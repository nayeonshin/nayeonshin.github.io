---
title:  "Reflections on Stanford Code in Place 2021"
excerpt: "I never felt the weight a teacher carries before. Teaching is not just a transfer of knowledge."
categories:
  - Writing
tags:
  - Python
  - Reflections
---

# Summary

No summary. My experience with this program is too good to be summarized with a few words, so please read this post till the end. 😉 This is probably going to be a pretty long post. I'm going to write down as many things as possible, from how I got into the program and what I think about the program. At the end, I've included my honest thoughts and feelings about my experience. Spoiler: Being a Section Leader was really, really difficult or me.

# What's Stanford Code in Place?

> A free, human-centric, intro-to-coding course in the time of COVID-19

[Stanford Code in Place](https://codeinplace.stanford.edu/) (often abbreviated as "CiP" or "CIP") is a free, 5-week-long coding program hosted by Stanford University, which was created in response to the COVID-19 lockdown. It is the first half of CS106A: Programming Methodology, which is a introductory level Computer Science course at Stanford taken by hundreds of Stanford students every year. Anyone from any countries who's 18 years old or older can join the program, either as a Section Leader (if you have a programming background) or student. By "a programming background," I mean that if you know the fundamental concepts in Computer Science , such as variables, if/else statements, loops (If you have them, you can pick up Python quickly even if you haven't used it before), you're eligible to become a Section Leader. There were roughly about 1000 Section Leaders and 10000 students this year, I think. (I'm not sure.) More information is on their website (Please click on the "Stanford Code in Place" hyperlink in the beginning of this paragraph).

# Why learn to code?

This is the first FAQ on the CiP website. According to the CiP team:

> It's fun and helps you get a job that you can do from home. It makes you think deeply and is perhaps the closest thing we have in this world to magic.

This is very true, but if I get asked the same question, I'd answer a little differently. Other than the fact that it's fun, helps you get a remote job, and makes you think deeply, let me answer this by bringing a [question asked on Naver Jisik-iN](https://kin.naver.com/qna/detail.nhn?d1id=13&dirId=130103&docId=347082562&qb=OTA4&enc=utf8&section=kin.qna&rank=711&search_sort=0&spq=0), which is like the Korean version of Quora:

> (Translated) Q. Please list the factors of the numbers from 1 to 1000.

> (Translated) A. Factor of 1: 01, Factors of 2: 01, 2, ..., Factors of 1000: 01, 2, 4, 5, 8, 10, 20, 25, 40, 50, 100, 125, 200, 250, 500, 1000

If you don't know how to code, you'll need to pull up a calculator and try to find and write down all the numbers. It'll take forever for you to complete the task. So, what can simplify this tedious process?

As you might have guessed, it's coding. If you know how to code, you can automate boring stuff. The responder of the question apparently used Python for it, which is a programming language that you can learn at Code in Place. (So sign up for CiP when it's open!) Not only can you do this, but you can also do other super fancy and cool stuff. This is a list from [csrankings.org](http://csrankings.org/#/index?all&us):

All Areas

AI

- Artificial intelligence
- Computer vision
- Machine learning & data mining
- Natural language processing
- The Web & information retrieval

Systems

- Computer architecture	
- Computer networks	
- Computer security	
- Databases	
- Design automation	
- Embedded & real-time systems  	
- High-performance computing	
- Mobile computing	
- Measurement & perf. analysis 	
- Operating systems	
- Programming languages	
- Software engineering	

Theory

- Algorithms & complexity	
- Cryptography	
- Logic & verification	

Interdisciplinary Areas

- Comp. bio & bioinformatics
- Computer graphics
- Economics & computation
- Human-computer interaction
- Robotics
- Visualization

Don't know what all of these are about? Neither do I, actually. But I just wanted to show that **there are just so many things in the world you can do with the ✨ magic ✨ of coding**. Even if none of these sound interesting as of now, why don't you just try learning coding? You'll have something to show off to your friends or family. If this sounds too childish (I think it does), the program is free, after all. It's an incredible learning opportunity you don't want to miss out on.

# My experience

## How I got to know the program

I really wanted to become a Computer Science teaching assistant at my school. But since I'm an international student currently located outside of the US, my school couldn't hire me due to some US labor laws. I even asked people if I would be able to work unpaid (because money is not the reason I want to be a TA; I just like helping people, especially with Python), and they said it's not possible. So, I was voluntarily helping a friend taking Data Structures in Python in the spring term. And I ended up really liking to do their assignments (although I didn't do their assignments *instead*). I thought I'd want to help more people learn Python. Then, a friend who joined CiP in 2020 as a Section Leader let me know about the program on LinkedIn. They even said they could refer me to the program. I was like, why not?

## How I got in

I read through the program description and filled out "Section Leader Application for Code in Place 2021" on Google Forms. The survey consisted of:

### 1. Tell-me-about-yourself questions

> Tell us about yourself (briefly, just a few sentences)

> What teaching experience do you have? (It's ok if you don't have any teaching experience!)

> What programming experience do you have? Also mention if you have programmed in Python - it's fine if you haven't!

Just write who you are. Here I mentioned that I wanted to become a TA at my school.

### 2. Debugging a piece of code

I'm going to include my answers here as well, but if it becomes problematic, please leave a comment on this post. I'll get rid of this part.

> The next two questions are about the following buggy student code. You are allowed to run the code, but we encourage you to focus on the student's intention.
>
> ```python
> def main():
>  dictionary = {}
>  dictionary["learning"] = "awesome"
>  dictionary["coding"] = "fun"
>  # ... Fill with more data
>  remove_keys_containing_string(dictionary, "learn")
> """
> This Python function takes in a dict and a string
> and removes all keys containing that string from the dict
> """
> def remove_keys_containing_string(dictionary, remove):
>  toRemove = None
>  for key in dictionary:
>      for i in range(len(key)):
>          if key[i:i+1] == remove:
>              toRemove.add(key)
>  if toRemove != None:  
>      for key in toRemove:
>          del dictionary[key]
> ```

This is the code I needed to debug. But I think the docstring should be inside <code>remove_keys_containing_string</code> function, though.

> A) Identify the problem(s) in the student's code for remove_keys_containing_string

> *My answer:*
>
> 1)
>
> ```python
> for key in dictionary:
> 	for i in range(len(key)):
> 		if key[i:i+1] == remove:
> ```
>
> This if statement doesn't work. We can see why it doesn't by walking through the code.
>
> (1) Parameters: <code>dictionary = {'learning': 'awesome', 'coding': 'fun'}</code>, <code>remove = "learn"</code>
>
> (2) We iterate through for each key in dictionary, so the first key is <code>learning</code>. Its length is <code>8</code>. So i starts at <code>i = 0</code> and ends at <code>i = 8</code>. But range function doesn't contain the the right endpoint. So we execute the conditional statement 8 times, starting at <code>i = 0</code>. When <code>i = 0</code>, <code>i + 1 = 1</code>. We use slicing <code>key[i:i+1]</code>. But it only gets each character in the key and compare it to remove, which is not what we want to do.
>
> 2)
>
> <code>toRemove = None</code>... <code>toRemove.add(key)</code>
>
> The type of <code>toRemove</code> is <code>NoneType</code>. A <code>NoneType</code> object doesn't have the attribute <code>add</code>. The object that has it is [set](https://docs.python.org/3/tutorial/datastructures.html#sets).
>
> My solution (fixed code that works as expected):
>
> ```python
> def remove_keys_containing_string(dictionary, remove):
>  toRemove = set() # initialize an empty set
>  for key in dictionary:
>      if remove in key:
>         # if the string key has remove as its substring
>          toRemove.add(key)
>  if toRemove != None:
>      for item in toRemove:
>          # changed "key" to "item"
>          # b/c toRemove is a set (not required)
>          del dictionary[item]
> ```

I probably didn't need to fix all the errors and write new code without them. But I still wanted to do so to show my interest in Code in Place.

> B) Write 3 sentences of advice to the student who wrote this code. Rather than point out the bugs, consider how to guide the student toward diagnosing and correcting the problems on their own.

> *My answer:*
>
> Let's add <code>print(dictionary)</code> at the end of <code>remove_keys_containing_string</code> to check the result and see we get. We get <code>{'learning': 'awesome', 'coding': 'fun'}</code>, which is not what we want, right? Now, let's add more print statements to see what each line is doing, for example, <code>print(key[i:i+1])</code> before if <code>key[i:i+1] == remove:</code>.

### 3. Demo video of my teaching

> Record and upload a 5-minute demo of your teaching.
> Upload a 5-minute video of yourself teaching the Mars Weight problem. See [https://codeinplace.stanford.edu/teach/instructions](https://codeinplace.stanford.edu/teach/instructions) for information on preparing the video.

I will not upload the video I submitted here. But I managed to go through the concepts within five minutes, which was harder than I thought.

You'll hear back in about a week or so. If you get in, you'll get an [ACTION REQUIRED] email. Read the email carefully and follow the onboarding process before the deadline.

**For readers of this post who didn't get in:**

Honestly, I have no idea how I got in. I think the referral played a big role. Don't worry, it really is okay even if you didn't get in. I promise. I have been rejected from sooooo many other opportunities, including some TA programs. Don't let it get you down. I didn't (and I don't) let rejections discourage me, although they hurt. You'll have another chance to join CiP (if COVID-19 still exists even after 2021) and there are lots of other free coding-based volunteer programs. :)

## Week 0

### SL Welcome Session

SL stands for Section Leader. ~~I think a lot of people in the US love to shorten things way too much.~~ It was a 30-minute Section Leader welcome session to get the course overview and my role as a section leader. Attendance was not mandatory, but Section Leaders who weren't able to attend the synchronous sessions needed to watch the recorded version. I could make it, although it started at 6 am my time. The professors who initiated the program all looked and sounded so excited in the meeting. I love seeing enthusiastic people.

### First small group training workshop

I was assigned to a small teacher training team of around 15 people. The platform being used for all meetings (except for the Welcome Session) at CiP is called "ohyay." (Edit: I just talked to Julie (one of the professors) at 3 am my time and they told me "ohyay" means something like "Listen up!" in Spanish? or some language. I thought it was just "oh!" + "yay!" that had no special meaning.) There were two small group training workshops in total, which happened on Sundays my time. (You can choose when to meet according to your availability prior to the start of the program.)

I had no idea what was going on in the first workshop. I had two amazing teacher mentors. People in the meeting constantly mentioned words like "Karel" and "beeper," and I had no clue what they were talking about. It was because I didn't know I'd need to read some Karel documentations before the first training workshop. The teacher mentors pretended that we (Section Leaders) were students and led a session, and then we gave them some feedback. This way, we were able to put ourselves in the students' shoes and think about what teaching methods worked well and what didn't. Another workshop happened after the first section.

![Karel](https://web.stanford.edu/class/archive/cs/cs106a/cs106a.1208/img/assn/karel.png)

*Figure 1. Karel*

What is Karel?

> In the 1970s, a Stanford graduate student named Rich Pattis decided that it would be easier to teach the fundamentals of programming if students could somehow learn the basic ideas in a simple environment free from the complexities that characterize most programming languages.

It's the character you see in the first week of CiP. You get assignments to move Karel and put beepers along the way.

![Karel and a beeper](https://compedu.stanford.edu/karel-reader/docs/images/ch1/world.png)

*Figure 2. Karel and a beeper*

## Week 1

### First section

The day before my first section, I stayed up all night reading through a lot of documents to familiarize myself with class materials and how CiP sections work. I think about 8 students came to my first section. I was quite nervous and didn't do well in my first section. I was mistaken about what <code>front_is_clear()</code> does and wasted some minutes figuring it out.

Topics covered:

- Welcome and functions
- Control flows

## Second small group training workshop

We were asked to bring a pen and paper. I met with my small group on ohyay and we had a moment to reflect on each of our first sections. We were divided into several breakout rooms and shared our thoughts. 

> 1) Who were the people in your section?
>
> My answer: Some of them seemed to be college students, and they come from different countries. That's all I knew.

> 2) What are the general demographics in your section? (age, location, gender, ethnicity, prior experience, languages):
>
> My answer: They are surely 18 or older. My sectionees are from Mexico, Japan, India, Malaysia, etc. Some people looked like they had already learned coding. Not all of us (myself included) speak English as the first language. (And I didn't comment on their genders and ethnicities because I didn't want to make assumptions.)

> 3) How was the level of student engagement?
>
> My answer: It was quite low, although I always tried to encourage them to participate. They looked quite shy and didn't really speak up. So, I asked them to use the emojis and reactions in the left bottom on the ohyay screen.

> 4) Who was participating?
>
> My answer: There were two students who were the most active. Others didn't even turn on their cameras, as far as I remember.

> 5) How can you replicate the strategy used to introduce that moment in the remaining sections?
>
> My answer: Student engagement is key. I should first introduce them to make mistakes and errors because it will let us think about what errors we have, what cause them, and how we can fix them.

> 6) What was the biggest challenge?
>
> My answer: It was inviting students to actively participate.

> 7) What can you do to transform this challenge for your next section?
>
> My answer: I should probably speak less. Maybe instead of me going over the class materials covered each week, I should ask students to share what they have learned.

My answers were not good. But still, answering the questions helped me redirect my approach to teaching.

Then, the teacher mentors presented possible situations with slides that could happen during a section and gave us a chance to think about how we would react in each circumstance. We went to breakout rooms again and wrote our answers in a group on the shared slides. One thing I remember is (I don't remember it word by word, though):

> Why is it not a good policy that students should promptly notify the section leader if they feel offended by the leader's remarks or behavior.
>
> Our answer (I answered this with the members in my breakout room):
>
> The student who's offended might not feel comfortable sharing what's offensive to them in front of other classmates. Also, if they just directly tell the leader, it can interrupt the entire section and result in a waste of time.

## Week 2

I saw a sharp decrease in the number of sectionees who attended my section (lol). It's probably because I did bad in my first section. But this time, I managed to go over everything and finish the section assignments on time. Week 2 is when students transition to Python from Karel. Starting from this week, I got a 5/5 in my student feedback. When you finish each section, students leave feedback and give a rating out of five.

Topics covered:

- Karel decomposition
- Python variables
- Python expressions

A sectionee made a private post that they were having a hard time transitioning into Python. That made me really worried. I also struggled a lot when I just started learning how to code. I just told them it'd be fine, but I wish I could have done something more.

## Weeks 3 & 4

I don't remember any particular things that happened during weeks 3 and 4.

Topics covered in week 3:

- Control flow revisited
- Functions revisited
- More parameters

Topics covered in week 4:

- Images
- Lists

Oh, it was surprising to see that they learn image processing in Code in Place and CS106A at Stanford (Remember that CS106A is the CS course students take at first). That's what I learned in an upper level CS course. So, I showed the week 4's section participants the image processing assignment I did. I briefly told them how we can implement the blur filter.

## Week 5

This was the last section. Two sectionees appeared and we first shared what our CiP experience has been. They said it's not easy but fun. I shared that I came to the conclusion that I don't want to pursue teaching as my profession thanks to Code in Place (Not because my experience was bad!).

Topics covered:

- Strings
- Dictionaries
- Files

Then we said goodbye. It was a good experience.

## T-shirt contest

I also submitted something to the T-shirt contest, which couldn't even make it to the top 10. 🤪 But it was fun, which is all that matters in Code in Place. After all, I wasn't even serious when I decided to give it a try!

![My t-shirt design]({{ site.baseurl }}/assets/images/posts/2021-05-22-my-t-shirt-design.jpg)

*Figure 3. My t-shirt design*

Yeah I have to admit it's too simple to be a good t-shirt design. I'm not a very creative person but at least I tried to be creative. You can see I drew a butterfly using the text "code."

# Thoughts after the program

Woah, finally I've reached this part. As I mentioned in the beginning of this post, being a Section Leader was a lot more difficult than I expected. I applied thinking teaching would be a very easy task, but I was completely wrong. The nights before each of my sections, I just could not go to sleep. I always stayed up till my section started. I wasn't even doing anything productive other than reading what's new on the Ed platform (where people in CiP make posts and comments). I was scared.

I was scared that my section would be a waste of time for my sectionees. A lot of students weren't coming to my section as time progressed. Am I not doing well? Am I not good of a Section Leader? Am I wasting their time? I felt really bad for being my sectionees' Section Leader. If you know me well, you probably know that I always strive to put as much effort as possible into the things I genuinely care about. I really cared about my sections and sectionees. I wanted to do well. But I was and I am too inexperienced to have the title of a Section Leader.

If I wasn't full of self-doubt, I would have been able to make slides on my own (as some other Section Leaders did), conduct polls and collect students' feedback on Google Forms (other than the feedback they submit on ohyay), and hold more office hours. I've helped one student with their first assignment, and that was the only help I gave. I don't know. Teaching is much much harder than I thought. I don't even know how teachers, instructors, and professors teach people in the virtual setting, which I think makes things more challenging.

I think I kind of tried to run away, fearing and doubting everything. Honestly, I can't help but think I only did the minimum required work. I didn't even watch all the lectures and do all the assignments on my own. 😥

But it's okay, although I don't know it really is. I tried (kinda). I'm not even good at English but this was my first time giving a lecture, especially in English. It would have been abnormal if I did well on my first try.

# How I can improve

I was going to name this part "What I could have done better," but that kind of shows my regret and sounds a little negative. So I changed it to "How I can improve (next time)." Some things I can do next when I try to tutor people are:

- Make interesting slides or some visual aids. Personally, I'm not a fan of slides but in such settings, slides that can attract listeners' attention would be of great help.

- More participant engagement. This is probably the hardest part. If I call out a particular student and ask them to answer a question, they can be embarrassed. Then, what should I do instead? 🤔

  I just quickly read an article ["15 Actionable Strategies for Increasing Student Motivation and Engagement"](https://www.gettingsmart.com/2016/08/15-actionable-strategies-for-increasing-student-motivation-and-engagement/) and here are my thoughts.

  When I made some mistakes, I think that taught students that I'm also human, and that I make mistakes. That was when they were most active in terms of participation. Building an authentic relationship will let students feel comfortable talking to the instructor and escalating issues. I also learned that personalized education is important because everybody learns in a different way.
  
  I also failed to conduct my own survey on Google Forms, just because students couldn't open the form I set up for some reason. I should get to know how to properly use Google Forms.

# Conclusion

The three keywords I'd choose to describe my first CiP experience are: "Challenging," "fun," and "bonding." One of the greatest things about CiP is that thousands of people gather at the same program with the interest in programming and Python. I bet the course is challenging for people who haven't learned coding for sure, but it's a really rare course in that its ultimate purpose is for everyone to have fun. I also truly enjoyed Code in Place, although everything felt so new and complicated. ㅠ______ㅠ If the pandemic still lasts and CiP opens its door again in 2022, I'm sure I'll become a Section Leader again and have been much more prepared.

This is not a good post but I appreciate you reading this post. Thank you! And thank you to all the Section Leaders, Instructors, and Staff in Code in Place. You're all amazing people. I look up to you all.
