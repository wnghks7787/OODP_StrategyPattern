# Object-Oriented Design Pattern - Strategy Pattern
### Goal
    - Understand how to encapsulation about change of algorithm
    - Understand how to deal change of algorithm with Strategy Pattern
    - Understand key points about Strategy Pattern with example.

## Example Situation
Let's assume that we are making Robots. We have two robots, ***Robots.Atom*** and ***Robots.TaekwonV***.
They are each have *Attack* and *Move* methods.
Robots.Atom can punch to attack and fly to move.
Robots.TaekwonV can missile to attack and walk to move.

### Code Ver_1
First, you can draw UML Class diagram like this:

<img width="400" alt="image" src="https://github.com/wnghks7787/OODP_StrategyPattern/assets/74361097/38059049-002e-4e1c-876e-229f2665393e">

#### Problem
- If I want to change existing robot's attack/move methods, how can I reach there?
  - For example, How can I make Robots.Atom to attack with missile?
- How can I make new robots, for example new-mighty *Sunguard* and give Robots.TaekwonV's missile attack system?

### Code Ver_2
Modified: Robots.Atom can only walk instead of flying.

#### Problem
- You need to modify existing code because of new function. It against OCP(Open/Closed Principle)
- Robots.Atom Class and Robots.TaekwonV Class has same code. It occurs redundancy.
  - It is hard to maintain consistently when number of robots increases.

### Code Ver_3
Now, let's add new robot, *Sunguard* !

<img width="400" alt="image" src="https://github.com/wnghks7787/OODP_StrategyPattern/assets/74361097/a8bef10e-303e-44a0-b578-fbdf461163e7">

#### Problem
- If new *Sunguard* wants existing moving / attacking process, we need to code it everything again.
- If we have new moving / attacking process, we need to modify whole codes.

#### Solution
- You need to find where to change.
  - In this case, *Attack* and *Move* .
- Encapsulate it (Make methods to Class!).
- Hide move / attack class for client.
- Make ***Interface*** for *Attack* and *Move* .
- Make class for run these things.

<img width="600" alt="image" src="https://github.com/wnghks7787/OODP_StrategyPattern/assets/74361097/b6ba42f9-f7b8-41ae-8175-c5ef1920ca3a">

As we can see this diagram, Robots.Robot need to access only Attack Strategy and Moving strategy.
When we need to add new Attack process, we can just add new class implement with *Attack Strategy* .
We don't need to modify Robots.Robot Class for change new strategy.

## Strategy Pattern
Strategy Design Pattern is the pattern that can easily change your strategy.
In this case, the term *Strategy* means "Algorithms or business rules that can reach some goals".
We can use this pattern when we need to change our strategy easily. Especially in game, we can use this pattern to use player's attack or act strategy.

Many algorithms which can solve same problems are encapsulation and we can just change this to make easy to solve problem.

### Collaboration

<img width="500" alt="image" src="https://github.com/wnghks7787/OODP_StrategyPattern/assets/74361097/242ca44a-3860-4787-b229-1254573e700e">

- Strategy: Notice that how can call algorithm outside of the interface / abstract class.
- ConcreteStrategy: Real Algorithms that noticed in strategy pattern.
- Context: Use strategy pattern. If needed, it can change concrete strategy, so it provide setter method.

자료 출처: 정인상, 채홍석. *자바 객체지향 디자인 패턴: UML과 GoF 디자인 패턴 핵심 10가지로 배우는*. 한빛미디어.