---
title: "Foundations of Data Intensive Applications"
date: 2021-10-27T00:00:00-00:00
authors: ["Jovan Sardinha"]
---

* How have applications changed in 2020s from the earlier days? What are the usual limiting factors?
  * Model applications are `data bound` as opposed to `compute bound`.
  * Most of the bottlenecks arise from fetching/setting and manipulating data.
* What are the typical building blocks that provide common functionality in modern applications?
  * Databases
  * Caches
  * Search Indexes
  * Stream Processing
  * Batch Processing
* The following tools {databases, queues, caches, etc...} each store data for different duration of time. Hence, why are these all grouped under the umbrella term of `data systems`?
  * There are a lot of tools that have emerged in recent years that are optimized for a particular used case. These tools do not fit into the traditional categories.
  * Many applications have a wide rage of needs that a single *database* tools cannot satisfy. Instead, it's better to break down tasks and let the best tool handle the sub-component.
  * When you combine several tools to provide one service, the service hides and syncs all these data tools from the client.  Now you have created a new, special-purpose data system from smaller general-purpose components.
* What is the difference between a *fault* and a *failure*?
  * A failure is caused when the system stops providing service to its clients.
  * A fault is when a component of a system deviates from spec.
* What are the main concerns of modern applications?
  * *Reliability*: The system should continue to work correctly even in the face of adversity.
  * *Scalability*: As the system grows (data volume, traffic volume, complexity, etc...), there should be reasonable ways of dealing with such growth.
  * *Maintainability*: Over time, different people will work on the system and they need to be able to contribute productively.

#### Reliability

* Things that can go wrong are called `faults`. Systems that anticipate faults and can copy with them are called `fault-tolerant` or `resilient`. A `failure` is when the systems as a whole stops providing service to it's customers.
* Types of faults and failures:
  * **Hardware Faults**
  * **Software Errors**
  * **Human Errors**

#### Scalability

* Two types of scalability issues:
  * **Load**: Params that best describe the stocks (storage) and flows (read/writes) in the system.
  * **Performance**: Best scribed in percentiles (Pxx) of service response time.
* Approaches for dealing with load:
  * [Horizontal scaling vs. vertical scaling](https://en.wikipedia.org/wiki/Scalability#Horizontal_(scale_out)_and_vertical_scaling_(scale_up))
  * Elasticity: See section on *partitioning*

#### Maintainability

* Design principles of software maintainability:
  * **Operability**: How easy is it for operations teams to keep the system running smoothly?
    * Understand what *tasks* the operations teams are responsible for (see p. 19-20 for suggestions).
    * What tools would help the operations team with the above tasks (see p. 20 for suggestions).
  * **Simplicity**: How easy is it for new engineers to contribute?
    * Related: Brian Foote and Joseph Yoder: “Big Ball of Mud,” at 4th Conference on Pattern Languages of Programs (PLoP), September 1997. from the `references` section.
  * **Evolvability**: How easy is it to change the system in the future?
    * No good framework provided here.
    * Might want to dig in more in other books (example. [Building Evolutionary Architectures: Support Constant Change](https://www.amazon.com/_/dp/1491986360?tag=oreilly20-20))
