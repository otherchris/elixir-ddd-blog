## OO vs. FP
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
- Create
### Things to notice



### DDD
