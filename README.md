
## Representation of a Real-World Problem as a Markov Decision Process (MDP)

### Aim

To represent a food delivery robot system as a Markov Decision Process (MDP) by defining its states, actions, rewards, transition probabilities, and Python representation.

---

## Problem Statement

### Problem Description

A food delivery robot delivers food orders inside a restaurant or hospital. The robot must decide the best path to reach the customer's location while avoiding obstacles and minimizing delivery time. The objective is to deliver the food safely and quickly with maximum efficiency.

---

## MDP Components

A Markov Decision Process is represented as:

$$
MDP = (S, A, P, R, \gamma)
$$

Where:

| Symbol | Meaning |
|---|---|
| $S$ | Set of states |
| $A$ | Set of actions |
| $P$ | Transition probability function |
| $R$ | Reward function |
| $\gamma$ | Discount factor |

---

## State Space

The possible states of the robot are:

```text
S = {
    Waiting for Order,
    Moving,
    Obstacle Detected,
    Delivering Food,
    Delivery Completed
}
```

---

## Sample State

```text
**Moving**

The robot is travelling toward the customer's location.
```

---

## Action Space

The possible actions of the robot are:

```text
A = {
    Move Forward,
    Turn Left,
    Turn Right,
    Stop,
    Deliver Food
}
```

---

## Sample Action

```text
 **Move Forward**

The robot moves one step closer to the delivery destination.
```

---

## Transition Probability

The transition probability describes the likelihood of moving from one state to another after performing an action.

[
P(s'|s,a)
]

Example:

* Moving → Delivering Food after **Move Forward** = **0.9**
* Moving → Obstacle Detected after **Move Forward** = **0.1**

---

## Reward Function

The reward function provides feedback to the robot based on its actions.

[
R(s,a,s')
]

Example:

* Successful delivery = **+20**
* Reaching destination = **+10**
* Hitting an obstacle = **−10**
* Delay in delivery = **−5**

---

## Graphical Representation


<img width="1536" height="1024" alt="mdp image" src="https://github.com/user-attachments/assets/0f6af28b-d78b-4179-9fc4-7922efebf50f" />





## Python Representation

```python
# MDP Representation using Python

print("Name: Mythri Ekkaluri")
print("Register Number: __________")

states = [
    "Waiting for Order",
    "Moving",
    "Obstacle Detected",
    "Delivering Food",
    "Delivery Completed"
]

actions = [
    "Move Forward",
    "Turn Left",
    "Turn Right",
    "Stop",
    "Deliver Food"
]

transition = {
    "Waiting for Order": {
        "Move Forward": "Moving"
    },
    "Moving": {
        "Move Forward": "Delivering Food",
        "Turn Left": "Obstacle Detected",
        "Turn Right": "Moving"
    },
    "Delivering Food": {
        "Deliver Food": "Delivery Completed"
    }
}

rewards = {
    ("Waiting for Order", "Move Forward"): 5,
    ("Moving", "Move Forward"): 10,
    ("Moving", "Turn Left"): -10,
    ("Moving", "Turn Right"): 2,
    ("Delivering Food", "Deliver Food"): 20
}

print("States:", states)
print("Actions:", actions)
print("Transitions:", transition)
print("Rewards:", rewards)
```

---

## Output

```text


States:
['Waiting for Order', 'Moving', 'Obstacle Detected',
 'Delivering Food', 'Delivery Completed']

Actions:
['Move Forward', 'Turn Left', 'Turn Right',
 'Stop', 'Deliver Food']

Transitions:
{
 'Waiting for Order': {'Move Forward': 'Moving'},
 'Moving': {
     'Move Forward': 'Delivering Food',
     'Turn Left': 'Obstacle Detected',
     'Turn Right': 'Moving'
 },
 'Delivering Food': {
     'Deliver Food': 'Delivery Completed'
 }
}

Rewards:
{
 ('Waiting for Order','Move Forward'): 5,
 ('Moving','Move Forward'): 10,
 ('Moving','Turn Left'): -10,
 ('Moving','Turn Right'): 2,
 ('Delivering Food','Deliver Food'): 20
}
```

---

## Result

The food delivery robot problem was successfully represented as a Markov Decision Process by defining its state space, action space, transition probabilities, reward function, and Python implementation. This model helps the robot make optimal decisions to deliver food efficiently while avoiding obstacles.




---

