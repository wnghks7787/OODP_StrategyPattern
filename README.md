# Object-Oriented Design Pattern - Strategy Pattern
### Goal
    - Understand how to encapsulation about change of algorithm
    - Understand how to deal change of algorithm with Strategy Pattern
    - Understand key points about Strategy Pattern with example.

## Example Situation
Let's assume that we are making Robots. We have two robots, ***Atom*** and ***TaekwonV***.
They are each have *Attack* and *Move* methods.
Atom can punch to attack and fly to move.
TaekwonV can missile to attack and walk to move.

### Code Ver_1
First, you can draw UML Class diagram like this:
<img width="400" alt="image" src="https://github.com/wnghks7787/OODP_StrategyPattern/assets/74361097/38059049-002e-4e1c-876e-229f2665393e">

#### Problem
- If I want to change existing robot's attack/move methods, how can I reach there?
  - For example, How can I make Atom to attack with missile?
- How can I make new robots, for example new-mighty *Sunguard* and give TaekwonV's missile attack system?