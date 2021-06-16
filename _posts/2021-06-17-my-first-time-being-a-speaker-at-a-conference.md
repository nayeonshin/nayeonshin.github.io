---
title:  "My First Time Being a Speaker at a Conference"
excerpt: "I led a Python workshop at Women Who Code CONNECT REIMAGINE 2021."
categories:
  - Writing
tags:
  - Events
  - Reflections
---

## So... I spoke at a conference

Jeez... It still doesn't feel real. [I just attended a conference for the first time about a month ago]({{ site.baseurl }}writing/my-first-pycon/), but now I'm someone who has spoken at a conference. Yes, I led a workshop at WWCode CONNECT REIMAGINE 2021 last Friday (Friday, June 11, 2021)!

How it all happened:

It was just a coincidence. I'm an active volunteer at Women Who Code Python Track. I was planning to present the two sessions about heaps and graphs, continuing the "Intro to Data Structures with Python" series. All the sessions in the series start at 9 am on Fridays Korea Standard Time. But the other week, the track people asked if I'd be willing to lead my heaps session at [WWCode CONNECT REIMAGINE 2021](https://connectreimagine.womenwhocode.dev/).

CONNECT (a.k.a. "CONNECT REIMAGINE," "WWCode CONNECT," etc.) is an annual inclusive developer conference hosted by Women Who Code. Just like most conferences, CONNECT 2021 happened online. Following the schedule of the series, my original session was scheduled to start at 9 am on Friday, June 11, 2021 Korea Standard Time. But it was when CONNECT would be taking place as well. Because the times overlapped, the Python Track people suggested that I deliver the session at CONNECT. They said it could be either a workshop or a session at the Python booth. I hesitated a bit, thinking I wasn't professional enough to speak at a formal conference. Then, I was like, "Score, why not?"

This is how the "Intro to Data Structures with Python: Heaps" started.

![Intro to Data Structures with Python: Heaps]({{ site.baseurl }}/assets/images/posts/2021-06-17-heaps-session.png)

## Preparation

I needed to brush up on my rusty heaps knowledge. I just utilized the resources I used in my Data Structures series: my professor's slides, the textbook, and a few other resources. I thought it would take hours just making the slides for the workshop, since I struggled with heaps so much when learning about them for the first time.

### Agenda

1. Queues & Trees Review
2. Priority Queue
3. Heap
   1. Binary Heap
   2. Structure Property
   3. Order Property
   4. Heap Operations
   5. Implementation
4. Q&A
5. Live Coding
6. Resources

You can view the slides on [Google Slides](https://docs.google.com/presentation/d/1q1RA4FExkOABv2ZNe3WJwsnLOdfWgmWZMVnclFI46SM/edit?usp=sharing) or [Slideshare](https://www.slideshare.net/NayeonShin1/session-7-heaps-wwcode-intro-to-data-structures-with-python-series).

## Workshop

Shermaine and Archana were with me helping with chat moderation. (Thanks guys you were my life savers. ily) I started by introducing myself and Shermaine and most importantly, the code of conduct at WWCode. Before getting started, I talked to Shermaine and Archana for a few minutes and that seemed to have created some confusion to attendees. I really should have used Slack, but it was a good lesson.

### Conceptual presentation

![Slides]({{ site.baseurl }}/assets/images/posts/2021-06-17-slides.png)

Since the concepts of priority queues and heaps are pretty much based on queues and trees, I thought it would be useful to include a Queues & Trees review. As a non-fan of slides, I tried to minimize the contents on every slide and replace them with images if possible.

![Trees review]({{ site.baseurl }}/assets/images/posts/2021-06-17-trees-review.png)

As specified [Problem Solving with Algorithms and Data Structures with Python](https://runestone.academy/runestone/books/published/pythonds/index.html), I defined trees in two ways which were by using nodes and edges and utilizing the idea of recursion.

![Priority queue]({{ site.baseurl }}/assets/images/posts/2021-06-17-priority-queue.png)

![Heap]({{ site.baseurl }}/assets/images/posts/2021-06-17-heap.png)

Then, I went over the highlights of the session: priority queues & heaps!

![Binary heap example]({{ site.baseurl }}/assets/images/2021-06-17-binary-heap-example.png)

I wanted to draw a good binary heap using the SmartArt on PowerPoint but dang, it was so hard to manipulate the nodes and edges as I wanted. So I gave up on it and drew it like an ASCII art.

![Binary heap implementation]({{ site.baseurl }}/assets/images/posts/2021-06-17-binary-heap-implementation.png)

I concluded the theoretical part with how to implement a binary heap using lists in Python! The table is so colorful, and it was actually adopted from my professor Valerie's slides. (If you're reading this (I kind of hope it's not because it'll be embarrassing), thanks so much Valerie! I should've asked if it would be fine to use that idea.. but I forgot to do so 🤯 Sorry about it.)

![Q&A]({{ site.baseurl }}/assets/images/posts/2021-06-17-q&a.png)

Before moving onto live coding, I paused a while and let attendees ask questions. I expected people would ask questions about heaps per se, but it looked like they were more curious about me as a presenter and my background. 🤣

### Live coding implementation

![Live coding]({{ site.baseurl }}/assets/images/posts/2021-06-17-live-coding.png)

Yes, it came. THE LIVE CODING. You have no idea how anxious I was before and every second of doing it. Here, I ended up not being able to catch an error I had in <code>heapify</code> method. It was really embarrassing and made me feel bad, but thank God how nice the attendees were! They were incredibly understanding and encouraging (more like forgiving for me being unprofessional). I wholeheartedly thank every single person who has attended my session, whether or not you engaged in the chat. Thank you!

After the workshop, I managed to fix the code. I also edited the code on [Colab](https://drive.google.com/file/d/1DMjHnlLhb4b-KoqiGx7OaudAwRdLX5WY/view?usp=sharing). Another mistake I made in the live coding part was that I should have shared link from the "share" button. But what I did was to simply copy and paste the link on the upper part of my tap. ~~What an idiot.~~

Here's the code with the bug fixed!:

```python
def heapify(self, i):
        """Restore max heap property starting at position i and working down 
        recursively"""
        left_index = (2 * i) + 1
        right_index = (2 * i) + 2
        max_index = i # Temporary initialization

        if left_index < len(self.heap) and self.heap[left_index] > self.heap[max_index]:
          max_index = left_index
        if right_index < len(self.heap) and self.heap[right_index] > self.heap[max_index]:
          max_index = right_index

        if max_index is not i: # If i is not the max, heapify
          self.swap(max_index, i)
          self.heapify(max_index)
```

The problem was with the comparison in <code>self.heap[left_index] > self.heap[max_index]</code> and <code>self.heap[right_index] > self.heap[max_index]</code>. I think what I initially wrote was something like

```python
if left_index < len(self.heap) and self.heap[left_index] > self.heap[i]:
          max_index = left_index
        if right_index < len(self.heap) and self.heap[right_index] > self.heap[i]:
          max_index = right_index
```

Notice that I'm comparing <code>self.heap[i]</code> instead of <code>self.heap[max_index]</code>. The reason we need to use the latter is that we're updating <code>max_index</code> to the largest item. And to do so, <code>self.heap[max_index]</code> should be used.

![Next session]({{ site.basurl }}/assets/images/posts/2021-06-17-next-session.png)

The next session is actually scheduled to be on June 24 Pacific time (if I'm not wrong). It's about graphs, and I'm the one who'll also be leading the session!

## Final thoughts

I just want to say thank you to everyone who made this workshop possible. Thank you Rishika, Shermaine, and Archana for assisting and supporting me from the preparation to demo and this workshop. Thank you all the attendees for sparing your precious time to attend my workshop!

Live coding turned out to be much much much harder than I thought. But it was great experience. Also, because of how an online workshop is, it felt really weird, awkward, and scared when I was sharing my screen and speaking. It was because I was worried if the attendees couldn't see my screen because of some error. Also because honestly, I felt like I was alone in the workshop somehow since there was no interactivity with the attendees other than the chat.

I'm really feeling the importance of writing a reflection post as soon as an incident happened. The memories are fading away, just like how a queue (FIFO) data structure works.

Thank you very much for reading, and I'll be back with other posts about Python Regex (I'll really write about this this time) and possibly my internships!

