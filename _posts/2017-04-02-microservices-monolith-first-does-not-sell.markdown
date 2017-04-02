---
layout:	post
title:	"On microservices&#58; Monolith-first does not sell"
date:	2017-04-02 21:07:00 +0100
---

Microservices, how amazing are they? Everyone seems to be talking about microservices and jumping on the bandwagon producing an insane quantity of them. People are proudly announcing the number of microservices that they have deployed and wearing it like a badge, as if the higher the number of microservices, the better<sup>[1](#footnote-1)</sup>. The amount of noise surrounding microservices within the tech world is enough to cause the cynical to be cautious of microservices being yet another tech hype. After the entire conundrum on how monoliths are bad and service-oriented architecture (SOA) makes everything more complex, microservices is the tech world’s (yet) another attempt at trying to make applications more robust and manageable.

While I was looking into the topic of microservices, I stumbled upon [an article by Martin Fowler](https://martinfowler.com/bliki/MonolithFirst.html) discussing the two different camps of people arguing how microservices should be done:
1. The monolith-first approach, or,
2. The microservice-first approach.

Before we start talking about the main topic of this article, there is one last thing that we need to understand in advance: bounded contexts.

Bounded contexts
----------------
What are bounded contexts? It is a core concept in domain-driven design (DDD) and it’s not an easy concept to explain. The simplest explanation that I’ve found is from the book *Building Microservices* by Sam Newman which he in turn sourced it [from SapienWorks](http://blog.sapiensworks.com/post/2012/04/17/DDD-The-Bounded-Context-Explained.aspx). “A bounded context is a specific responsibility enforced by explicit boundaries.” It pretty much follows that bounded contexts encourage modularity at the right level and identifying them is an arduous job. Get them right and you’re all set; get them wrong and the consequences can be terrifying - overcoupled components, cross-service changes needed when a business change is required, and complex spaghetti interactions across services<sup>[2](#footnote-2)</sup>. If one were to split bounded contexts based on an ill-understood business domain, it is only a matter of time until he/she discovers that instead of gaining all the advertised advantages of moving to a microservices architecture, the business might end up at a worse footing from where it had started.

Monolith-first approach
-----------------------
People in this camp argue for a monolith-first approach to developing backend applications i.e. by building a monolithic application first and splitting the application out into microservices once the bounded contexts of the application are clearly identified. As most microservices projects are greenfield projects, the team members are usually new to the business domain of the software being developed and they should not start by building microservices first. Even if the team members are used to the business domain, identifying bounded contexts can be a difficult task and splitting the services up in the wrong way would incur a heavy technical debt which would turn out to be a massive problem in the future. People in this camp would rather trade-off some initial time upfront than pay a hefty penalty in the long term by building a monolithic application to understand the business domain better before splitting the application into the many different individual microservices.

Microservices-first approach
----------------------------
People who support the microservice-first approach argue that by going straight into developing microservices, the developers can get the team into the rhythm required to support the implementation of microservices especially if the concept of microservices is new to the team. The resources and skills required to support the development and maintenance of microservices are usually different to the conventional way of how monolithic software are managed (in terms of application implementation, deployment, and monitoring) and it is better to get the team to dive straight into microservices so that the team can learn on the job. The microservice-first approach also allows the business to scale up its development efforts easily as each team only has to focus on its capability’s delivery and not worry about stepping on each other’s toes. Having said that, the scalability of development efforts is not unique to microservices as monolithic application with modular components can enjoy the same benefits.

Monolith-first does not sell
----------------------------
No one knows which camp is right but I personally lean on the monolith-first approach. I am of the opinion that we should start out by building a monolith application first and only migrate to a microservices platform once the bounded contexts of a business domain are slowly identified. As the saying goes, “[duplication is far cheaper than the wrong abstraction](https://www.sandimetz.com/blog/2016/1/20/the-wrong-abstraction),” comes to mind. Extending from the same logic,  “a monolith is easier to manage than a suite of microservices with the wrong bounded contexts.”

The ultimate question that needs to be answered is this: how would you sell a monolith-first application to a business? As software engineers, we need to realise the fact that software development comes with a financial cost. Who is going to pay the bill for the team to slowly identify the bounded contexts? Which business is going to be sold on the idea of “let’s build a monolith first and we’ll slowly move to microservices” because obviously, promises to improve technical systems are always realised<sup>[3](#footnote-3)</sup>? What is going to get a business to be excited about microservices when the advantages of microservices cannot be observed from the very start? Unless you have excellent salesmanship, it will be an uphill battle in trying to sell the monolith-first approach to businesses as the advantages of one approach over another are difficult to quantify.

I have yet to see a project that started from a monolith-first approach. Netflix who seems to have popularised the concept of microservices - although they don’t seem to have invented the term “microservices” - regard themselves as employing a fine-grained SOA. Hopefully, this “let’s dive deep into the business domain and split work out as we go approach” does not cultivate an abhorrence of businesses from microservices projects that end up in failure<sup>[4](#footnote-4)</sup>.

In Dave Thomas’s presentation [Agile is Dead](https://www.youtube.com/watch?v=a-BOSpxYJ9M), he argues that *“Agile”* has completely lost its original meaning and it’s now used as a marketing tool for consultancies to sell their consultancy services. I’m afraid *“Microservices”* is heading in the same path and someone else will come up with something new and shiny and tell us that we’ve been doing everything wrong the whole time.

<br />
<br />

------------
<a name="footnote-1">[1]</a>: Of course, some business domains warrant more microservices than other business domains. It all boils down to the complexity of the business.

<a name="footnote-2">[2]</a>: This is not unique to microservices. Badly modularised applications can bring the same annoyance.

<a name="footnote-3">[3]</a>: For those who aren’t familiar with the tech world, the correct answer is: never. Promises to improve an IT system are always made but never realised - purely an anecdotal experience but I believe many software engineers would agree with me.

<a name="footnote-4">[4]</a>: Any tool or idea taken to its extreme can bring disaster and I’m afraid microservices might end up being a tale of horror to be told to our posterity just because someone over-applied the concept.
