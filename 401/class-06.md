# How to use Random Module
* Random module provide you with various  methods to get what you want from generating random numbers.
* list of methods the random module provides:
  * Randint
  generates random integer number between two values. the first value should be less than the second value.
  ```python
  import random
  print random.randint(0, 5)
  This will output either 1, 2, 3, 4 or 5
  ```
  * Random
  generates a random value between 0 and 1. we can then multiply it by any number to get large value.
  ```python
   import random
   random.random() * 100
  ```
  * Choice 
  return a random value from a sequence.
  ```python
  import random
  myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]
  random.choice(myList)
  ```
  * Shuffle
  shuffles the values in list in place so the order will change.
  ```python
  
  from random import shuffle
  x = [[i] for i in range(10)]
  shuffle(x)
  Output:
  # print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]
  # of course your results will vary
  ```
  * Randrange
  return a random number from a range.
  ```python
  import random
  for i in range(3):
    print random.randrange(0, 101, 5)
  ```

# What is Risk Analysis in Software Testing and how to perform it?
* The Risk analysis in software testing is the process of identifying the risks in application and give them preorities.
* using risk analysis at the beginning identify the risk areas which helps the developer to decrease the risk effects.
* The possiblity risks that might appear: 
  * Use of new hardware
  * Use of new technology
  * Use of new automation tool
  * The sequence of code
  * Availability of test resources for the application
* there are some risks we cant avoid them like incomplete requirments or defect due to complexity of the application. in such cases there are some points we should follow.
* Conduct Risk Assessment review meeting

* Use maximum resources to work on high-risk areas

* Create a Risk Assessment database for future use

* Identify and notice the risk magnitude indicators: high, medium, low.

* Risk Identification.
  
  * Business Risks: It comes from your business not from project

  * Testing Risks: you should be familiar with testing tools you are using.

  * Premature Release Risk: you should know the risks of realising first version of your application.

  * Software Risks: you should know the risks you might encounter during software development.

* Risk Assessment
There are some perspective of the risk assessment

  * Effect : to asses the risk based on its  effect
  * cause : to asses the risk based on its cause.
  * Likelihood  : to asses the risk based on probability of some requirments will not be satisfied.

* How to perform Risk Analysis?
  * Searching the risk
  * Analyzing the impact of each individual risk
  * Measures for the risk identified

# TestCoverage
* Test coverage is the process of measuring the percentage of untest parts of the codebase.
* Test coverage of 100% is a suspicious 
* Test coverage between 80% and 90% will be satisfied If you are testing thoughtfully and wel.
* Test coverage below half is a sign of problem.
* you can do enough testing if the following is true:
  * `You rarely get bugs that escape into production, and`
  * `You are rarely hesitant to change some code for fear it will cause production bugs.` 






## References 
[How to use the Random Module in Python](https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python)

[What is Risk Analysis](https://www.edureka.co/blog/risk-analysis-in-software-testing/)

[Test Coverage](https://martinfowler.com/bliki/TestCoverage.html)
