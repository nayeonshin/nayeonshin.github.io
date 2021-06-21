---
title:  "How to Send an Email Using Java"
excerpt: "Even sending an email was hard... for me"
categories:
  - Study
tags:
  - Java
---

## Motivation

I've tried following multiple instructions on how to send an email using Java, but nothing worked except for the code below.

## Requirements

1. You need a <code>.jar</code> file, which is <code>javax.mail.jar</code>. You can download it [here](https://javaee.github.io/javamail/). Then, add it to the <code>CLASSPATH</code>. If you don't know how to do so, refer to [these instructions](https://www.geeksforgeeks.org/how-to-add-jar-file-to-classpath-in-java/).

2. You need to enable "less secure app access" in Google account settings, which is opted out by default:

   ![Less secure app access]({{ site.baseurl }}/assets/images/posts/2021-06-22-google-settings.png)

**Disclaimer: this code isn't written by me only. I adopted most parts from the Internet.**

Let's get right into the Java code:

```java
import java.util.Properties;
import javax.mail.Authenticator;
import javax.mail.Message;
import javax.mail.PasswordAuthentication;
import javax.mail.Session;
import javax.mail.Transport;
import javax.mail.internet.InternetAddress;
import javax.mail.internet.MimeMessage;

public class SendGmail {
	public static void main(String[] args) {
		String mailProtocol = "smtp";
		String mailHost = "smtp.gmail.com";
		String mailPort = "587";
		String mailId = "abc@gmail.com"; // Google email address (Sender)
		String mailPassword = "abc"; // Google account password (Sender)
		
		String fromName = "abc"; // Sender's name
		String fromEmail = "abc@gmail.com"; // Sender's email address

		String toName = "def"; // Receiver's name
		String toEmail = "def@gmail.com"; // Receiver's email address

		String mailSubject = "Subject"; // Email subject
		String mailContents = "Contents"; // Email contents

		String debugMode = "false";
		String authMode = "true";

		try {
			boolean debug = Boolean.valueOf(debugMode).booleanValue();
			Properties mailProps = new Properties();

			mailProps.put("mail.smtp.starttls.enable", "true"); // Must use true for gmail
			mailProps.setProperty("mail.transport.protocol", mailProtocol); 
			mailProps.put("mail.debug", debugMode);
			mailProps.put("mail.smtp.host", mailHost); // smtp server host
			mailProps.put("mail.smtp.port", mailPort); // Gmail port
			mailProps.put("mail.smtp.connectiontimeout", "5000");
			mailProps.put("mail.smtp.timeout", "5000");
			mailProps.put("mail.smtp.auth", authMode); // Must use true for gmail

			Session msgSession = null;

			if (authMode.equals("true")) {
		        Authenticator auth = new MyAuthentication(mailId, mailPassword);
				msgSession = Session.getInstance(mailProps, auth);
			} else {
				msgSession = Session.getInstance(mailProps, null); 
			}

			msgSession.setDebug(debug);

			MimeMessage msg = new MimeMessage(msgSession);

			msg.setFrom(new InternetAddress(fromEmail, fromName));
			msg.setRecipient(Message.RecipientType.TO, new InternetAddress(toEmail, toName));
			msg.setSubject(mailSubject);
			msg.setContent(mailContents, "text/html; charset=euc-kr");

			// Sends it to the object and close the object
			// instead of sending it directly to the static function
			Transport t = msgSession.getTransport(mailProtocol);
			try {
				t.connect();
				t.sendMessage(msg, msg.getAllRecipients()); // Sends email
			} finally {
				System.out.println("Email successfully sent");
				t.close();
			}
		} catch(Exception e) {
			e.printStackTrace();
		}
	}
}

class MyAuthentication extends Authenticator {
    PasswordAuthentication pa;
    public MyAuthentication(String mailId, String mailPass) {
        pa = new PasswordAuthentication(mailId, mailPass); // Enters ID and password
    }
    // Authentication info used in the system
    public PasswordAuthentication getPasswordAuthentication() {
        return pa;
    }
}
```

I added comments so it should be self-explanatory.

## What is smtp?

SMTP stands for Simple Mail Transfer Server. It's "an internet standard communication protocol for electronic mail transmission," according to Wikipedia. In order for you to send an email using Java, you need it. Then, why is that?

![SMTP]({{ site.baseurl }}/assets/images/posts/2021-06-22-smtp.png)

When we send an email, it goes to an SMTP server. Then, the SMTP server delivers the email to the recipient.

## Thoughts

I don't know if it's just me but the fact that sending an email using Java is that complicated shows how difficult coding is. Maybe it's just for me. But I'll keep learning!

Thanks for reading, and please leave a comment if you have any questions or feedback. Bye for now!