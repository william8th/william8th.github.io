---
layout:	post
title:	"Lessons Learned as a Software Engineering Graduate (1)&#58; Write your godd*mn tests!"
date:	2016-08-15 20:38:05 +0100
---

"Did you read Osborne's Autumn Statement on the papers this morning on how house taxes are calculated when you buy a house? Doesn't matter if you didn't. So here's the question: write a program that calculates the correct amount of taxes an individual has to pay given a property's price as an input. Before we start programming, let's write some tests."

This was the question that I was given by my interviewer for a potential job. We were doing a pair-programming exercise and my mind went blank for the first time in a job interview.

"Write some tests? What do you mean by writing some tests? What tests?"
Questions started popping into my head as I was thinking of the solution to the problem. Tests? Why waste unnecessary time writing tests? What are tests anyway? I've been programming on and off for five years and I have only heard of them mentioned perfunctorily in university lecture slides or in the titles of blog posts that I've never clicked on.

"Err... Okay..."

"Yeah, let's write the tests first. Now, how would you write the tests for this calculator program?"

I didn't know back then that this was test-driven development (or TDD abbreviated). Why do you even need tests? All you need to do to see if your code works correctly are simple:

1. Write some code for the program.
2. Run the program in such a way that it triggers the bit of code that you've just written.
3. Verify if it ran to your expectation. If it did, well done. If it didn't, fix your code.

Programming was this easy for me. Write some code and verify if it works. Tests? No one needs tests. Why do you need tests? You can test it yourself.

"Ain't nobody got time for that"
--------------------------------
It's all about hackathons for the young and naive me. Hacking is cool, building something in a limited amount of time is cool, learning *x* language in *y* minutes is cool. TDD? Yucks, get that boring thing out of my face!

I was fresh out of university thinking that all code was written and tested manually. As long as the [happy path](https://en.wikipedia.org/wiki/Happy_path) works, nothing else matters. The closest real-world experience that I had ever had was my internship in a small mobile application agency whose software engineering capabilities weren't quite as mature. Understandably, for a small-scale enterprise that they were, an application that ships is what's most important and I salute them for that. They didn't have TDD in mind and probably wouldn't have been happy with not seeing any "real" progress. They taught me a lot in terms of mobile application programming but I later found out that there was more to programming than just manually testing if the happy path works.

Now that I have graduated and landed myself a job as a software engineer in a company where almost all of its employees keep on hammering on and on about tests, I was caught offguard thinking that I had already learned everything there is to know in software engineering. It turned out that I didn't know anything about software testing.
I still remember the first lesson that I had attended at the software engineering academy that the company has set up. "How would you know if your code works? You have to first write some tests to prove that your code was what made the tests pass. That's how you can make sure that your code is bug free." It seemed silly to me that I have to write some tests first and make sure that they *fail* before I move on to writing code to make the tests pass. I wasn't used to such a foreign concept. **It felt like coding suddenly became more scientific - a hypothesis is assumed false unless proven otherwise - and it felt like the practice of software engineering became much more rigorous.**

I started reading up more on TDD. I looked up stuff online, talked to people, and I was slowly making more friends who are preachers of TDD. It felt so right and yet so simple. How do you know if your code works? Well, by testing it.

I still remember one of the most important quotes that I had stumbled upon while looking into what people mean when they say legacy code: What is legacy code? What makes a piece of code legacy? This was a question posted on Stack Overflow that will undoubtedly bring about very opinionated answers. One of the answers was this: [What do you call legacy code? Untested code.](http://programmers.stackexchange.com/questions/94007/when-is-code-legacy/94011#94011)

The answer struck me in so many different ways. If you'd actually written tests to guard against expected conditions, you would be sure that the code that you've written would definitely work fine for the situation that you've tested against when your application is live. Of course, the number of states increases exponentially as you increase the number of variables in your application so there's just no way to test against all possible state permutations. TDD doesn't eliminate bugs, it reduces them.

After attempting to do TDD for some time now, I've found myself actually taking my time to think about the problem at hand before writing any code unlike the old me who will jump at the problem and write boilerplate code that doesn't matter most of the time. I've seen quite a few programmers who don't do any planning beforehand and just jump straight at the problem. They would later find out that what they had programmed does not fit the acceptance criteria and there will be tons of bugs to be found. I know this because I was one of them. Writing code with your nimble fingers flying across the keyboard banging on the keys makes me feel satisfied as though it quenches a dying thirst of mine for the clicky keyboard sounds. Now that I look back at the old me, it feels wrong. I dived into the problem without thinking. People say that coding is akin to solving a puzzle. What puzzle can be solved without thinking?

Writing good code is a result of an engineer's habit
----------------------------------------------------
Now that it's been almost a year since I started as a graduate, I slowly realise that the quality of code that an engineer produces is always a result of an engineer's habit. If an engineer is careful with her code, she would always analyse all the possible situations and gaps that are not considered. If an engineer only cares about "real" results and what is shown on the screen, it's most likely that error handling is an afterthought and not handled correctly, if handled at all.

A piece of functionality is not comprised of just the happy paths. **There are parts of the code that can fail which *will* fail.** It's the engineer's responsibility to make sure that all possible situations are thought through.
TDD is not just about error handling. TDD is about disciplining a software engineer into handling the different states that a software can be in. That's why tests are important. Tests to show that the happy paths work, tests to show that errors are handled correctly, tests to make sure that the code we have written is true to our expectations.

"Yeah, so let's start writing the tests."

My fingers were on the keyboard but it's not dancing across the keys like it used to. It's not moving. I didn't know what I was supposed to do.

"I don't know how to write tests. Can you please guide me?"

I started my TDD journey during an interview. The blessings of the Testing Goat was upon me...

Side note: If you want to start doing TDD but don't know where to begin, I'd strongly recommend Harry J.W. Percival's *[Obey the Testing Goat](http://www.obeythetestinggoat.com/)*. I started the book with limited Python skills so even if you're not a Python master, it doesn't matter. It's a step-by-step book that will slowly bring you into the world of TDD. It's available free online and if you really enjoy it, get yourself a copy!
