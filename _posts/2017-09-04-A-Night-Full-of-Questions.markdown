---
layout: single
title: "A Night Full of Questions"
date: 2017-09-04 00:22:00 +0530
excerpt: QnA for SnT Code in Takneek, the technical fest of IIT Kanpur. 
tags: puzzles science-coffeehouse
comments: true
---
A few days back, SnT Code, one of the biggest events of Takneek 2017, was organised. For the uninitialized, Takneek is the intra-college technical festival of IIT Kanpur. All the clubs under the Science and Technology (SnT) Council have to make questions that the rest of the campus can then try and solve. I participated in Takneek in both my first and second years and this time I made the questions for the hobby group I co-lead, Science Coffeehouse. 

Solutions to the questions follow if you scroll down, so if you don't want spoilers, don't scroll down before taking whatever tries you want to take. All bouquets and brickbats for the questions to be directed at me, please. If they feel esoteric, they were supposed to be solved by some of the brightest of the campus residents with the full power of Google at their fingertips and (nearly) unlimited time. They are supposed to remain hard to solve in such surroundings. If you are unsure as to what exactly the paragraphs of text want, look deeper, and try and see something more than what is obvious. I have experimented with some of my friends, and some of them did get the answers to the second and third questions without serious trouble. The first question is, in my opinion, the hardest one. 

Another disclaimer seems relevant here. The questions here may not exactly match what was asked in the event itself, but the minor changes you might find do not change the answer or the process used to arrive at the answer.

# Questions

## Question 1

**"Refer to the fitting resource you can find on the biggest encyclopaedia"**

![Question 1](../assets/photos/SnT_Code_Q1.JPG)

## Question 2

### A Theoretical-Computer-Scientist/Physicist Rants...

Isn't machine learning too applied? What is it that attracts people to a field like that? Xkcd was correct (https://xkcd.com/1838/), you know. It is just a whole lot of numbers in multidimensional arrays that you keep throwing about here and there. Every time someone tries to explain that stuff to me, I feel like a burnt wick! You might think I am not normal. I agree! I often spend hours thinking I am Spiderman, swinging from building to building and webbing people up. Is webbering even a word? If it is, that is what I would like to call it. Well, I deviated from the topic under discussion. Or, as I would like to put it, I got tangentially away from the things I was planning to say. The stone called machine learning hangs like a heavy load from my neck - because almost everyone around me is doing only that and nothing else! Just go and do some real math, guys! Heat up a metal plate. See how the heat spreads. Heat it up, even more, see how it bends? Can you calculate how all that is going to happen? Even though these problems are years and years old, these are the cool ones! Heated vessels sound boring, right? No, the math is interesting, satisfying! Try doing those calculations quickly though - you don't want to be stuck on it forever, right?

I shall meander away again. If these people are kind enough, I would love to have a theorem or law named after me. It would be so cool if I could be remembered for a lifetime right? Right, man? That would be awesome! I hear you say, I have heard this before. You kid all the time!. No, no, I love Math! Look at this Cera basin, isn't the curvature lovely? I am digressing again! Let's meet again, right?

*[All views expressed in the above are of a fictional character only. The creator of this question has no animosity towards machine learning of any form whatsoever]*

## Question 3

### 'We are freaks, oddities! We drive the world forward precisely because we are, but if we come together, we go together!'

So in your quest to look closely at the oddities in the world, you have reached Kolkata, nicknamed the City of Joy or the City of Palaces. The names have varying sources - City of Joy comes from a book by Dominique Lapierre, and City of Palaces comes from the abundance of colonial-era architecture in the city. After all, it was the capital of British India longer than Delhi was, and was also one of the biggest trade centres of the British Empire. It is also the city where Ronald Ross did his Nobel Prize-winning work on malaria, and CV Raman did the majority of his work on light. However, you do not want to keep thinking about Science all the time, so you ask a trusted friend to guide you to the sights in the city. Your guide takes you on a walk down central Kolkata, near an open green area what is called the Maidan, and tells you that you are actually walking in the heart of the old British city. Among the colonial era buildings to be seen in the area, chief are the Victoria Memorial, Fort William, and the St. Pauls Cathedral. Your guide first takes you into the cathedral. It was the first cathedral built in the British Empire outside England itself, and it is currently the seat of the Diocese of Calcutta. Your guide shows you around the main altar and the library, and you are hooked by its Indo-Gothic architecture. You can see the Victoria Memorial outside, and you are a little surprised - why was it built in Calcutta, a provincial city and not the capital in Delhi? Your guide takes a moment, and launches into a long account of the early 19th century when increased nationalism in Bengal forced the British Indian Empire to move the capital to Delhi. Work on the Memorial, he says, started before the shift, so they could not move it. Incidentally, says the guide, the shift occurred just a year after Mark Twain died. You are surprised by the tangential reference - does it have any meaning? The guide assures you that he brought up the name just because Twain is his favourite author. He recommends to you the Twain's travelogue - Following the Equator - where he has some typical witticisms about things that he saw in the country. You assure him that you will try and read the book, and you part with a spring in your step having just spent an amazing evening. You promise to meet again the following day, where your guide would take you on another quest through the tons of new stuff to see in a new city!

There is, however, something that is bothering you. Why did the guide insist on that particular walk? And, more importantly, who doesn't find Twain-ish witticisms irritating?


# Solutions

## Question 1

The first question has a pretty obvious Harry Potter reference in the text to the right of the matrix. It is the message that first appears when someone uses the Marauders' Map, just with the names and the terms changed. The biggest encyclopaedia is obviously Wikipedia, so we are now in possession of two clues.

Now, someone might go down the Harry Potter route and get totally lost, but I thought that a square with an HP reference would suggest 'magic square'. Also, if someone reads books, and has ever read Dan Brown's excellent 'The Lost Symbol', they would probably put 'cryptograph' and 'magic square' together to guess that the decryption has to be done using a magic square.

The question now is how to find the magic square. We require a 12 x 12 magic square, and the only thing that can help us now is the Wikipedia reference. If you visit the Wikipedia page for magic squares, you will find two 12 x 12 magic squares. In the worst case, you will need to try both. The encryption proceeded thus: I wrote a message in a  12 x 12 matrix, and numbered each square from 1 to 144, like this.

![original](../assets/photos/SNT1.PNG)

The magic square I chose had numbers from 1 to 144. If the entry at the position i, j of the magic square is k, then the letter at square k of the message square goes to the square i,j in the cryptogram. To decrypt, one has to simply reverse this process. Before shuffling, I also Caesar shifted each letter in the yellow boxes by 1 and converted to ASCII, so one has to reverse that too to finally solve it. I had to do this because otherwise, people could have tried to unjumble the yellow boxes only and guess what message they contain.

The magic square used is this

![magic square](../assets/photos/SNT2.PNG)

Once the decryption is complete, this is the result. The answer, Srinivas Ramanujan, should be obvious now. Also, the Queen in 'Cryptograph of the Queen' refers to Number Theory, which Gauss called the 'queen of Mathematics' and which Ramanujan worked on extensively.

![solution](../assets/photos/SNT3.PNG)

## Question 2

One of my friends solved this in about 5 minutes, and it should be trivial to anyone who knows anything about the history of science. The question has nothing to do with machine learning whatsoever, and that was intended simply to throw people off.

Starting from the last paragraph, it should be obvious that we are looking for someone who has something named after them, who probably worked on mathematics, and probably also worked on curvature. Towards the end of the first paragraph, there are hints that heat is also important to this problem.

The answer should now be obvious. Gauss's Law. Gauss worked on curvature and was the first person to suggest that non-Euclidean geometry is a thing. Historically, the mathematics of heat flow on a metal plate was the setting in which Fourier developed the theory of Fourier series, and solving it 'fast' is a reference to the fact that Gauss had discovered some form of the fast Fourier transform. The rest of the clues are a little less obvious, but in the first paragraph, there are references to a load on the neck, webbering and a burnt wick. The first two are supposed to hint at the magnets (also known as lodestones) and Gauss's work with them, and Gauss was born in Brunswick (I couldn't help a pun, could I?)

> The friend who solved this suggested that Riemann is probably a more natural fit in this question, and he has good reason to recommend that. In hindsight, I think so too.

## Question 3

Here I couldn't help dropping references to my hometown of Kolkata. However, the answer has nothing to do with Kolkata. The reason why I got to Kolkata was because of the existence of St. Paul's Cathedral in the city. The answer is however linked to the cathedral of the same name in London, which replaced an earlier cathedral that was destroyed in the Great Fire of London. The architect was Sir Christopher Wren, which will be important later.

Mark Twain was shoved in to relate to Halley's Comet. Mark Twain's year of birth and death are both years during which the Halley's Comet made an appearance. He also has a quote regarding this issue, a garbled version of which forms the title of the question. Halley will also be important in the solution.

The last reference is a little more veiled. The person being spoken to leaves with a 'spring in his step' and is 'hooked' by the architecture of the cathedral. These are oblique references to Robert Hooke, of Hooke's law fame. 

The three people above - Christopher Wren, Edmond Halley and Robert Hooke, met at a coffeehouse in London in January of 1684 and had a discussion regarding the nature of gravity. The things they discussed during the meeting prompted Halley to meet Sir Isaac Newton, who hadn't yet published the Principia Mathematica and had no intention to do so. Halley soon found out that Newton had formulated a full theory of motion and gravity and then pushed him to publish the Principia. In retrospect, the meeting in the coffeehouse was vitally important in the history of science. The answer to the question, then, is **coffeehouse**!
