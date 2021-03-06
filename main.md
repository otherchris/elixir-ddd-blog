## OO vs. FP
I want to be clear that this is not another OO vs. FP post. A fun way to make
yourself miserable is to google "OO vs FP" and start reading. Many, many words
spilt to say "IT DEPENDS".

The central misunderstanding of that conversation is that people are likely to
make a decision of functional or object oriented and then proceed to choose
languages, tools and design patterns relative to that decision.

I think its much more likely that this dependency is inverted. People choose
language ecosystems (or have that choice made for them) and retroactively
justify the paradigm that the ecosystem facilitates. I don't think this is
necessarily a bad idea, those types of choices are often made with important
considerations in mind.

What are the implicit assumptions behind those considerations though? Are they
valid?

I have a guess that there is an implicit assumption that leads a lot of large
enterprise software into the oo camp. That is that a clean, domain driven
architecture is most naturally expressed using class and objects.



- Overly academic
- Different ways of expressing a system, not correct or incorrect
- Have different advantages and disadvantages
- OO's (crumbling) hegemony outreaches its actual value

## The useful conversation
- We do have decisions to make
- I have a point of view, FP makes sense to me
- Say you have a system where the design is the problem (not having a design
  counts!). You're going to rebuild. You should compare _good_ design to _good_
  design, because your design is going to be good!

## The bias
- Eliminate concerns of state from your domain logic
- The "good stuff" about classes is that they are _types_.
- We'd like to be able to use the Actor model for concurrency

## The translation
- Where you have a class in OO, you have a type in FP
- Where you have an instance method in OO, you have a type -> type function in
  FP
- Your domain logic

## Meetings: an example
Here's an example domain that will be rich enough for us to illustrate with.
Suppose we need software that will facilitate meetings that adhere to some
formal rules of order (rro link). We want the software to present members with
the actions available to them, and to allow them to apply those actions,
updating the meeting as appropriate.

We do some event storming and see this.

We can see that we have an aggregate forming! There is a "meeting" that is
being acted upon.

### A Good OO Design
- The domain logic, `Meeting` class
  - Check if an action is valid
  - Apply to the state
- The use cases, commands/queries
- The controller, interface/api to the outside world

### Things to notice
- The domain class methods are self interested. Their behavior refers to
  `this`, the state of the meeting.

### A Functional Alternative
- Create a type for the aggregate
- Spread the domain logic over multiple modules, just bags of functions!
- Use language features like `@behaviour` to enforce your design
- Use tools like `dialyzer` to strengthen your types
- We use our high level description to drive our design
- The server stands in for the controller

### Things to notice
- All the same decoupling
- Stateless domain logic
- Persist state in an isolated process




### DDD
