<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name: Viswapriya S         </h3>
<h3>Register Number:  212225230311          </h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
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
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

<hr>
<h2>Sample Input and Output</h2>
<h2>Sample String:</h2> Artificial Intelligence
<h2>Output:</h2>
Score: 643  Solution :  8RzF:oG ]%;CPORRMe!zGvk<br>
Score: 609  Solution :  8RzF:oG ]%;CPqRRMe!zGvk<br>
Score: 604  Solution :  8RzF:oG ]%;CPqRRMe!zGqk<br>
Score: 594  Solution :  8RzF:oG ]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
....................................................<br>
..................................................<br>
................................................<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 0  Solution :  Artificial Intelligence<br>

## PROGRAM:
```
import random
import string

def generate_random_solution(answer):
    return [random.choice(string.printable) for _ in range(len(answer))]

def evaluate(solution, answer):
    return sum(abs(ord(solution[i]) - ord(answer[i]))
               for i in range(len(answer)))

def mutate_solution(solution):
    ind = random.randint(0, len(solution) - 1)
    solution[ind] = random.choice(string.printable)
    return solution

def SimpleHillClimbing():
    answer = "Artificial Intelligence"
    best = generate_random_solution(answer)
    best_score = evaluate(best, answer)

    while best_score > 0:
        new_solution = mutate_solution(list(best))
        score = evaluate(new_solution, answer)

        if score < best_score:
            best = new_solution
            best_score = score

        print("Score:", best_score, "Solution:", "".join(best))
        print("Solution:", "".join(mutate_solution(list(best))))

    print("Score:", best_score, "Solution:", "".join(best))

SimpleHillClimbing()
```

## OUTPUT:

<img width="1522" height="467" alt="WhatsApp Image 2026-10-21 at 9 00 44 AM" src="https://github.com/user-attachments/assets/beaef100-a736-4565-9d33-8144a4b67a8e" />

<img width="1531" height="460" alt="WhatsApp Image 2026-10-21 at 9 01 06 AM" src="https://github.com/user-attachments/assets/af78e5a1-c2d5-4f6f-9be5-07cd4fe8a4af" />

## RESULT:

Thus the Implementation of Simple Hill Climbing Algorithm is implemented successfully


