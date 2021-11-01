# In Tests We Trust — TDD with Python

* There is a difference between unit tests and TDD (Test Diriven Development)
  * unit tests are codes to exercie output against input of some code and to exercise how that code will behave.
  * TDD is how to write  unit tests and how to think about them before you start writing any feature

* Let us explain the example in the resource.
  * you are asked to implement api to identify the gender based on the name of customer.
  * first we need to write test and make that test fail.
  * we will write a test to female gender and the test will fail because we did not write any code in `run` method.
    ```python
        def test_should_return_female_when_the_name_is_from_female_gender():
                detector = GenderDetector()
                expected_gender = detector.run(‘Ana’)
                assert expected_gender == 'female'
    ```
   * then we need to make this test pass by implement `run` method.
    ```python
        def run(self, name):
            return 'female'
    ```
    * now the test will pass.
    * we need now to write test to identify the male gender.
    * ```python
        def test_should_return_male_when_the_name_is_from_male_gender():
                detector = GenderDetector()
                expected_gender = detector.run(‘Pedro’)
                assert expected_gender == 'male'
      ```
    * now the test will fail because the `run` method just return `female`.
    * we need to fixed that and refactor our code.
    ```python
        import requests

        def run(self, name):
                result = requests.get('https://api.genderize.io/?name{}'
            .format(name))
                return result['gender']
    ```
    * Now the the unit tests will pass.


# What does the if __name__ == “__main__”: do?
* the module is a python file and every file has a __name__ variable.
* the modules can either be reusable as imported in other modules or standalone program.
* if we run the module directly the __name__ variable for this module will be "__main__".
* if we imported the module from other module the __name__ variable will be the name of that module.
* By this way we can make a module  execute some code even if it was imported in other module.


# Recursion
* Recursion is calling function itself directly or indirectly.
* direct recursion is when the function calls itself directly inside its block, and indirect recursion when the function call anthor function and that function calls the first function.
* we used recurion proccess to solve probloms which are inherently recursive like tree traversals, Tower of Hanoi, because it provide a clean way to solve such those problems.
* We can resolve recurion algorithm using iterative approch and vice versa.
* every recurion problem must have a base condition.
* the base condition is the point of stopping calling the function itself.
* Some of disadvatges of using recurion is that it exhausts the memory when the number of calls is big since the memory allocate each call on the top of stack.
* To avoid solving a problem recursively we can use stack data structure.
* Ex.
```python
        # A Python 3 program to
        # demonstrate working of
        # recursion


        def printFun(test):

            if (test < 1):
                return
            else:

                print(test, end=" ")
                printFun(test-1) # statement 2
                print(test, end=" ")
                return

        # Driver Code
        test = 3
        printFun(test)

        # This code is contributed by
        # Smitha Dinesh Semwal

```
  ![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/recursion.jpg)
## References 
[In Tests We Trust — TDD with Python](https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)

[Recursion](https://www.geeksforgeeks.org/recursion/)