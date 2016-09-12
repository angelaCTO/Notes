#Debug It - Paul Butcher
---

###***1.0 : A Method In The Madness***
---
####***The Diagnosic Method***
  1. **Work out root cause of the issue**  
  2. **Fix the problem**  
  3. **Avoid breaking other things**  
  4. **Maintain and improve the overall quality of the code**  
    - Consider:    
      + Readability    
      + Architecture    
      + Test Coverage    
      + Performance      
  5. **Ensure the same problem is not occuring elsewhere and will not occur again** 
Else, introducing a ***regression***, ie breaking something that worked before some change, may be an imminent risk.

####***The Empirical Approach*** 
  - **Empiricism** relies on **observation** and experience, rather than pure theory or logic. In the context of sw, it means directly observing the behavior of the program.  

####***The Core Debugging Process***
  - **Reproduce** : 
    + Find a way to reliably and convieniently reproduce the problem on demand.  
  - **Diagnose** : 
    + Construct hypothesis, and test them by performing experiments until you are confident tht you have identified the underlying cause of the bug.  
  - **Fix** : 
    + Design and implement changes that fix the problem, avoid introducing regressions, and maintain and improve the overall quality of the software
  - **Reflect** : 
    + Learn the lessons of the bug and the fix. Where did things go wrong? How to ensure that the problem doesn't happen again?

####***Summary***
1. Construct experiments, and observe the results  
2. Debugging is an iterative process.
3. Ask: *"What is happening, and what should be happening?"*
4. One problem at a time.

---
---

###***2.0 : Reproduce***
---
Reproduce the problem *first*, before doing anything else. 
  1. ***Start with the obvious***
    - Follow bug report steps
    - Check the machine
    - Etc.
  2. ***Target your efforts - *Control****
    - If you can control all relevant variables, you will eventually reproduce the problem
    - **Software** : Ensure versioning is the same as reported in the bug report.
      - Compiling from the same source code does not garuntee that you will be running the same object code. 
      - You also need to ensure that you use the same compiler, configured the same way, and the same runtime libraries, as well as any third party code that is integrated with your SW. 
      - Use tools in the same manner, in exactly the right sequence and with the same configuration as the SW was originally built with.  
    - **Enviroment** : Consider differences between the user's external system and your own (e.g HW, remote server) and try to replicate the same enviroment.  
      - Your SW's enviroment is anything that might affect its behavior.
      - Consider differences:
        + OS
        + Other SW
        + Browser
        + HW
      - Create a virtual data center on a single machine by running several VM's in parallel.
    - **Inputs** : Replicate the original user's configurations
      - *Infer Inputs* : Assume the problem does exist, and reverse engineer the necessary conditions that would lead to the problem.
        - *Work Backwords* : Using what we know, then infer from ready facts
        - *Explore Coverage Landscape* :  
          - *Boundary Value Coverage* : Ex. input ranges, overflow, etc.
          - *Branch Coverage* : If you are unable to reoriduce a problem with a particular sequence of inputs, try creating inputs that excercise diference code branches in the same area. 
      - *Force Error Conditions* : Consider whether some error condition could have manifested somewhere in the process and try to force that error to manifest again or simulate the error.
      - *Introduce Randomness* : Explore a wider range of inputs by introducing variability. 
        - *Fuzzers* :
          - *Generators* : Generational Fuzzers built input based on a data model, either from scratch or by combining existing data in interesting ways. This data model encodes an understanding of the SW being tested in order to increase the chance of discovering problems.
          - *Mutation* : Mutating Fuzzers start from a known-good template that is then modified according to a set of rules. These rules are constructed in such a way as to increase the chance that the resulting input will uncover unknown SW problems.
     - *Recording Inputs* : Log the sequence
       - *Logging*
         - External Logging - Use Logging Proxy
       - *Load and Stress*
  
Refine the reproduction cycle
  - Minimize the feedback loop - you want to be able to run many experiments *quickly*
  - Aim for minimal reproduction
  - Make non-deterministic bugs deterministic
    - Non-determinism can only have a few causes :
        - Starting from an unpredictable initial state
      - Interaction with external systems
        - Best to not try to control external systems, rather replace it with something you can control eg. debugging subsystem, test double, etc.
      - Deliberate randomness
        - Randomness is pseudo-random, use the same seed to control "random" sequence
      - Multithreading
        - Disable multithreading

---
---

###***3.0 Diagnose***
---

***Construct a hypothesis and test them with experiments***  
  - Understand what the experiments are intended for - *what information will it provide you*?
  - Make one change at a time
    - Multiple changes confuse conclusions
  - Keep a record of past tests/attempts - pass/fail?
  - Don't ignore anything - any unexpected behavior encountered can be a lead
  - Anything you don't understand is potentially a bug

***Strategems***  
  - *Instrumentations* : Instrumentation is code that doesn't affect how the software behaves but instead provides insight into why it behaves as it does. (ex. logging)
    - The full facilities of the language are at your disposal (collect and collate data, evauate arbitrary code, test relevant conditions, etc.)
  - *Divide & Conquer / Binary Chop* : Use divide and conquer method to pinpoint root issue, at the very least, root area.
  - *Devil's Advocate* : Play the devil's advocate. Assume you are wrong and in doing so you avoid falling into psychologically self-sustained maintenance of your own beliefs (you see/believe what you want to see).
  - *Sherlock Holmes Principle* : *"When you have eliminated the impossible, whatever remains, however improbable, must be the truth"*
  - *Ocam's Razor* : All other things begin equal, the simplest explanation is usually the best.

***When things are not going well...***  
  - If the changes you made don't seem to produce an effect, you're most likely changing the wrong thing
  - Validate your assumptions
    - Assumptions may create blind spots, examine them critically
  - Multiple causes, shifting sands ... consider the problem is more complex than thought and refine technique to address this
  - Ask: *"Are you facing multiple interacting causes or changing an underlying system?"*
  - Ask for help - a fresh pair of eyes will do good, once in a while.
  
---
---

###***4.0 Fix***
---

***Bug fixing involves 3 goals :***
  1. Fix the problem
  2. Avoid introducing regression
  3. Maintain and improve overall quality of the code

***Start from a clean souce tree***  

***Ensure that all tests pass before making any changes***  
  - Tests will ensure your fix address the problem, but can act as safeguard against regression as well.
  - One of the rules of *Test-First Development* states not to modify anything unless you have a failing test
    1. Run the existing tests, and demonstrate that they pass
    2. Add 1+ test cases or fix the existing tests to demonstrate the bug (ie, to fail)
    3. Fix the bug
    4. Demonstrate fix works by showing that previously failed tests now pass
    5. Demonstrate no regression has been introduced by showing that all previous tests that passed still pass
  
***Work out how you're going to test your fix before making any changes***  

***Fix the cause, not the symptoms***  

***Refractor, but never at the same time as modifying functionality***  

***One logical change, check-in***  
  - Diff before check-in
  - Get your code reviewed  

---
---

###***5.0 Reflect***
---
