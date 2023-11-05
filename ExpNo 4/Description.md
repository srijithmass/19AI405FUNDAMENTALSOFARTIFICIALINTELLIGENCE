# Exp no 04 : IMPLEMENT SIMPLE HILL CLIMBING ALGORITHM
## NAME : SRIJITH R
## REGISTER NUMBER : 212221240054
## AIM:
Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration.
## THEORY:
Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
## ALGORITHM:

1. Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.
2. Loop until a solution is found or there are no new operators left to be applied in current state:
3. Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
4. Evaluate the new state:
  <ul>
  <li>if it is a goal state, then return it and quit</li>
  <li>if it is not a goal state but better than current state then make new state as current state</li>
  <li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>

## PROCEDURE:
### Step 1:
<p> Generate Random String of the length equal to the given String</p>

### Step 2:
<p>Mutate the randomized string each character at a time</p>

### Step 3:
<p> Evaluate the fitness function or Heuristic Function</p>

### Step 4:
<p> Loop Step 2 and Step 3  until we achieve the score to be Zero to achieve Global Minima.</p>

<hr>

## PROGRAM:
```PYTHON
import random
import string
def generate_random_solution(answer):
    l=len(answer)
    return [random.choice(string.printable) for _ in range(l)]
def evaluate(solution,answer):
    print(solution)
    target=list(answer)
    diff=0
    for i in range(len(target)):
        s=solution[i]
        t=target[i]
        diff +=abs(ord(s)-ord(t))
    return diff
def mutate_solution(solution):
    ind=random.randint(0,len(solution)-1)
    solution[ind]=random.choice(string.printable)
    return solution
def SimpleHillClimbing():
    answer="Artificial Intelligence"
    best=generate_random_solution(answer)
    best_score=evaluate(best,answer)
    while True:
        print("Score:",best_score," Solution : ","".join(best))  
        if best_score==0:
            break
        new_solution=mutate_solution(list(best))
        score=evaluate(new_solution,answer)   
        if score<best_score:
            best=new_solution
            best_score=score
#answer="Artificial Intelligence"
#print(generate_random_solution(answer))
#solution=generate_random_solution(answer)
#print(evaluate(solution,answer))
SimpleHillClimbing()
```
## OUTPUT:
![image](https://github.com/aakaashvp/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/75235212/9426e891-b056-4161-8d68-5be487985630)

## RESULT:
thus, implementation of Simple Hill Climbing Algorithm using python is executed successfully.
