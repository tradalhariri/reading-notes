# Dunder Methods
- Dunder methods are predifined methods which you can use them to enrich your class.
- It start and end with double underscore.
- The best example is `__init__` which is used to create instances of the class.
```python
class Account:
   

    def __init__(self, owner, amount=0):
       
        self.owner = owner
        self.amount = amount
        self._transactions = []
```
- what if we want to represent the object of the class as string . there are two dunder methods to do that job` __str__, __repr__`
```python
class Account:
    # ... (see above)

    def __repr__(self):
        return 'Account({!r}, {!r})'.format(self.owner, self.amount)

    def __str__(self):
        return 'Account of {} with starting amount: {}'.format(
            self.owner, self.amount)
str(acc)
Account of bob with starting amount: 10

print(acc)
Account of bob with starting amount: 10

repr(acc)
Account('bob', 10)

```

- we can also make the object iterable using `__len__, __getitem__, __reversed__`:
-----

```python
class Account:
    # ... (see above)
    def add_transaction(self, amount):
    if not isinstance(amount, int):
        raise ValueError('please use int for amount')
    self._transactions.append(amount)

    def __len__(self):
        return len(self._transactions)

    def __getitem__(self, position):
        return self._transactions[position]

acc = Account('bob', 10)

acc.add_transaction(20)
acc.add_transaction(-10)
acc.add_transaction(50)
acc.add_transaction(-20)
acc.add_transaction(30)
len(acc)
5

for t in acc:
  print(t)
20
-10
50
-20
30

acc[1]
-10

```

- conclusion: dunder methods are more powerful when we want to customize our objects.
----------
# Tutorial: Basic Statistics in Python — Probability


- What is probability? 
  Probability is a chance of an event to occures.
- In reality there is no ideal trial so we cant say in flipping a coin "the probability of getting head is 50% exactly" .  So we can use the statistics on our data to give us approximate probabilities.
```python 
import random

def coin_trial():
   heads = 0
   for i in range(10):
    if random.random() <= 0.5:
      heads +=1
   return heads
  
def simulate(n):
    trials = []
    for i in range(n):
      trials.append(coin_trial())
    return(sum(trials)/n)
    
print(simulate(10))
```
[example result](https://drive.google.com/file/d/1V1P5mf7vTsRb7gb1DYZEZPjpjPJMwC4_/view?usp=sharing)

- the example shows the more we increase the trials the more we get what we expect.

## References 
[Dunder Methods](https://dbader.org/blog/python-dunder-methods)
[Statistics - Probability](https://www.dataquest.io/blog/basic-statistics-in-python-probability/)


