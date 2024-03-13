## Introduction to AI

1. Who invented proto-computers in 19th century?
   1. Charles Babbage invented computers to **operate numbers following an algorithm**
2. What is the difference between **Weak AI and Strong AI**?
   1. **Weak Ai** is AI designed for a **small specific task** or **a narrow set of tasks**
      1. they do not have great understanding of consciousness, i.e. do not have human-like cognitive abilities.
      2. examples 3. Siri, Alexa, chatbots
   2. **Strong AI** is AI with human-level intelligence and understanding
      1. they can perform some complicated tasks that humans can do, adapt to different domains and new knowledge, and have a form of consciousness
      2. it is also a long-term goal of AI research and the current industry tries to develop AI that can **reason, learn, understand, and adapt to a wide range**
3. What is the **definition of intelligence**?
   1. it depends on how people think about the term
4. What is **Turing Test**?
   1. It is a test which compares between a system and human being. If a human interrogator cannot distinguish between these two based on text-based dialogue, then this system is considered to be intelligent.
5. What are some approaches to make computer behave like a human?
   1. these approaches are based on how our own processes of making decisions work
   2. **Top-down Approach (Symbolic Reasoning)**
      1. extract knowledge from a human and represent that knowledge in a computer-readable form
      2. like how doctors diagnose patients (applying a large set of rules)
      3. however, this approach does not have that great scalability
         1. complicated to extract & apply human knowledge
         2. too expensive
   3. **Bottom-up Approach (Neural Networks)**
      1. model the structure of human brain, where each neuron acts like a weighted average of its inputs
      2. then train a network of neurons to solve useful problems by providing **training data**
      3. a.k.a **Machine Learning**
   4. **Multi-agent Approach**
   5. **Evolutionary Approach**
6. When did AI start?
   1. during the mid 20th century

## Symbolic AI

- What is the **top-down approach**?
  - It is an approach where you **extract knowledge from people into some machine-readable form** and use it automatically to **solve problems**
- What are two big main ideas for top-down approach?
  - knowledge representation
  - reasoning
- What is **knowledge**, and how is it different from **information**?
  - Knowledge is something contained in our head, representing our understanding of the world
  - We can obtain knowledge through **active learning process**
  - It is different from **information/data** because we turn the information that we received into our active model of the world
- What is **DIKW Pyramid**?
  - Data << Information << Knowledge << Wisdom (left <- right; higher order)
- What is the **main goal of knowledge representation**?
  - finding some effective way to represent knowledge inside a computer in the form of data, to make it automatically usable
- How can we **classify knowledge representation**?
  - **semantic network**
    - network of interrelated concepts in our head = graph inside a computer
    - object-attribute-value triplets / attribute-value pairs (as node)
  - **hierarchical representation**
    - frame representation
      - representing each object / class of objects as a frame which contains slots
      - slot
        - have possible default values, value restrictions, stored procedures
      - frame
        - form a hierarchy
      - scenario
        - special kind of frames that represent complex situations that can unfold in time
  - **procedural representation**
    - a list of actions that can be executed when a certain condition occurs
    - examples
      - production rules
        - if-then statements
      - algorithm
  - **logic**
    - examples
      - predicate logic
        - statements whose truth value depends on one or more variables from any set
      - descriptive logic
        - empty, intersection, union, negation
- What is the **early success of symbolic AI**?
  - Expert system, a computer system designed to act as an expert in some limited problem domain!
- What are the main components in the **knowledge-based system**?
  - **problem/working memory**: (static) knowledge about the problem being currently solved
    - short-term memory, snapshot
    - contain the set of OAV triplets that correspond to the problem
  - **knowledge base**: long-term (dynamic) knowledge about a problem domain
    - manually extract from human experts
  - **inference /rules engine**: a component which orchestrates the whole process of searching in the problem state space + asking questions of the user when necessary + finding the right rules to be applied to each state
    - look for rules for which a condition is satisfied & apply them
- What are some processes that inference engines use?
  - **forward inference**
    - start with initial data about the problem available in the working memory
    - execute the following reasoning loop
      1.  target attribute in working memory? stop & give the result
      2.  look for all the rules whose condition is currently satisfied & get conflict set of rules
      3.  perform conflict resolution
          1. select one rule that will be executed on this step through one of hte following ways:
             1. select the first applicable rule
             2. select a random rule
             3. select a more specific rule
      4.  apply the selected rule & insert new piece of knowledge into the problem state
      5.  repeat from step 1
  - **backward inference**
    - start with an empty knowledge
    - ask questions until getting to the conclusion
    - process
      1.  select all rules (a conflict set), which are candidates for solving a goal (RHS)
      2.  no rules for the attribute? or rule stating that we need to ask? => then ask
      3.  select **one rule** using conflict resolution strategy
          1. use this rule as hypothesis
      4.  recurrently repeat the process for all attributes in the LHS (if part) of **the selected rule**, trying to prove them as goals
      5.  if the process fails, then select another rule on step 3 and repeat
