---
title:  "Reflections on Stanford Code in Place 2021"
excerpt: "I never felt the weight a teacher carries before"
categories:
  - Writing
tags:
  - Reflections
---

# Summary

No summary. My experience with this program is too good to be summarized with a few words, so please read this post till the end. 😉 This is probably going to be a long post.

# What's Stanford Code in Place?

> A free, human-centric, intro-to-coding course in the time of COVID-19

[Stanford Code in Place](https://codeinplace.stanford.edu/) (often abbreviated as "CiP" or "CIP") is a free, 5-week-long coding program hosted by Stanford University, which was created in response to the COVID-19 lockdown. It is the first half of CS106A: Programming Methodology, which is a introductory level Computer Science course at Stanford taken by hundreds of Stanford students every year. Anyone from any countries who's 18 years old or older can join the program, either as a Section Leader (if you have a programming background) or student. By "a programming background," I mean that if you know the fundamental concepts in Computer Science , such as variables, if/else statements, loops (If you have them, you can pick up Python quickly even if you haven't used it before), you're eligible to become a Section Leader. More information is on their website (Please click on the "Stanford Code in Place" hyperlink in the beginning of this paragraph).

# Why learn to code?

This is the first FAQ on the CiP website. According to the CiP team:

> It's fun and helps you get a job that you can do from home. It makes you think deeply and is perhaps the closest thing we have in this world to magic.

This is very true, but if I get asked the same question, I'd answer a little differently. Other than the fact that it's fun, helps you get a remote job, and makes you think deeply, let me answer this by bringing a [question asked on Naver Jisik-iN](https://kin.naver.com/qna/detail.nhn?d1id=13&dirId=130103&docId=347082562&qb=OTA4&enc=utf8&section=kin.qna&rank=711&search_sort=0&spq=0), which is like the Korean version of Quora:

(Translated) Q. Please list the factors of the numbers from 1 to 1000.

(Translated) A. Factor of 1: 01, Factors of 2: 01, 2, ..., Factors of 1000: 01, 2, 4, 5, 8, 10, 20, 25, 40, 50, 100, 125, 200, 250, 500, 1000

If you don't know how to code, you'll need to pull up a calculator and try to find and write down all the numbers. It'll take forever for you to complete the task. So, what can simplify this tedious process?

As you might have guessed, it's coding. If you know how to code, you can automate boring stuff. The responder of the question apparently used Python for it, which is a programming language that you can learn at Code in Place. (So sign up for CiP when it's open!) Not only can you do this, but you can also do other super fancy and cool stuff. This is a list from [csrankings.org](http://csrankings.org/#/index?all&us):

All Areas

AI

► Artificial intelligence
► Computer vision
► Machine learning & data mining
► Natural language processing
► The Web & information retrieval

Systems

► Computer architecture	
► Computer networks	
► Computer security	
► Databases	
► Design automation	
► Embedded & real-time systems  	
► High-performance computing	
► Mobile computing	
► Measurement & perf. analysis 	
► Operating systems	
► Programming languages	
► Software engineering	

Theory

► Algorithms & complexity	
► Cryptography	
► Logic & verification	

Interdisciplinary Areas

► Comp. bio & bioinformatics
► Computer graphics
► Economics & computation
► Human-computer interaction
► Robotics
► Visualization

Don't know what all of these are about? Neither do I, actually. But I just wanted to show that **there are just so many things in the world you can do with the ✨ magic ✨ of coding**. Even if none of these sound interesting as of now, why don't you just try learning coding? You'll have something to show off to your friends or family. If this sounds too childish (I think it does), the program is free, after all. It's an incredible learning opportunity you don't want to miss out on.

# My experience

## How I got to know the program

I really wanted to become a Computer Science teaching assistant at my school. But since I'm an international student currently located outside of the US, my school couldn't hire me due to some US labor laws. I even asked people if I would be able to work unpaid (because money is not the reason I want to be a TA; I just like helping people, especially with Python), and they said it's not possible. So, I was voluntarily helping a friend taking Data Structures in Python in the spring term. And I ended up really liking to do their assignments (although I didn't do their assignments *instead*). I thought I'd want to help more people learn Python. Then, a friend who joined CiP in 2020 as a Section Leader let me know about the program on LinkedIn. They even said they could refer me to the program. I was like, why not?

## How I got in

I read through the program information and filled out "Section Leader Application for Code in Place 2021" on Google Forms. The questions on the survey were:

### 1. Tell-me-about-yourself questions

> Tell us about yourself (briefly, just a few sentences)

> What teaching experience do you have? (It's ok if you don't have any teaching experience!)

> What programming experience do you have? Also mention if you have programmed in Python - it's fine if you haven't!

### 2. Debugging a piece of code

I'm going to include my answers here as well, but if it becomes problematic, please leave a comment on this post. I'll get rid of this part.

> The next two questions are about the following buggy student code. You are allowed to run the code, but we encourage you to focus on the student's intention.
>
> ```python
> def main():
>     dictionary = {}
>     dictionary["learning"] = "awesome"
>     dictionary["coding"] = "fun"
>     # ... Fill with more data
>     remove_keys_containing_string(dictionary, "learn")
> """
> This Python function takes in a dict and a string and removes all keys containing that string from the dict
> """
> def remove_keys_containing_string(dictionary, remove):
>     toRemove = None
>     for key in dictionary:
>         for i in range(len(key)):
>             if key[i:i+1] == remove:
>                 toRemove.add(key)
>     if toRemove != None:  
>         for key in toRemove:
>             del dictionary[key]
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
> (2) We iterate through for each key in dictionary, so the first key is '<code>learning</code>'. Its length is <code>8</code>. So i starts at <code>i = 0</code> and ends at <code>i = 8</code>. But range function doesn't contain the the right endpoint. So we execute the conditional statement 8 times, starting at <code>i = 0</code>. When <code>i = 0</code>, <code>i + 1 = 1</code>. We use slicing <code>key[i:i+1]</code>. But it only gets each character in the key and compare it to remove, which is not what we want to do.
>
> 2)
>
> <code>toRemove = None</code>... <code>toRemove.add(key)</code>
>
> The type of <code>toRemove</code> is <code>NoneType</code>. A <code>NoneType</code> object doesn't have the attribute '<code>add</code>'. The object that has it is [set](https://docs.python.org/3/tutorial/datastructures.html#sets).
>
> My solution (fixed code that works as expected):
>
> ```python
> def remove_keys_containing_string(dictionary, remove):
>     toRemove = set() # initialize an empty set
>     for key in dictionary:
>         if remove in key: # if the string key has remove as its substring
>             toRemove.add(key)
>     if toRemove != None:
>         for item in toRemove:
>             # changed "key" to "item" b/c toRemove is a set (not required)
>             del dictionary[item]
> ```

I probably didn't need to fix all the errors and write new code without them. But I still wanted to do so to show my interest in Code in Place.

> B) Write 3 sentences of advice to the student who wrote this code. Rather than point out the bugs, consider how to guide the student toward diagnosing and correcting the problems on their own.

> *My answer:*
>
> Let's add <code>print(dictionary)</code> at the end of <code>remove_keys_containing_string</code> to check the result and see we get. We get <code>{'learning': 'awesome', 'coding': 'fun'}</code>, which is not what we want, right? Now, let's add more print statements to see what each line is doing, for example, <code>print(key[i:i+1])</code> before if <code>key[i:i+1] == remove:</code>.

### 3. Demo video of my teaching

> Record and upload a 5-minute demo of your teaching.
> Upload a 5-minute video of yourself teaching the Mars Weight problem. See https://codeinplace.stanford.edu/teach/instructions for information on preparing the video.

I will not upload the video I submitted here. But I managed to go through the concepts within five minutes, which was harder than I thought.

You'll hear back in about a week or so. If you get in, you'll get an [ACTION REQUIRED] email. Read the email carefully and follow the onboarding process before the deadline.

## Week 0

### SL Welcome Session

SL stands for Section Leader. ~~I think a lot of people in the US love to shorten things way too much.~~ It was a 30-minute Section Leader welcome session to get the course overview and my role as a section leader. Attendance was not mandatory, but Section Leaders who weren't able to attend the synchronous sessions needed to watch the recorded version. The professors who initiated the program all looked and sounded so excited in the meeting. I love seeing enthusiastic people.

[To be continued]

## Week 1

## Week 2

## Week 3

## Week 4

## Week 5

# Thoughts after the program

# Conclusion

