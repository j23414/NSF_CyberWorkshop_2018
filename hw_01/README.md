# Homework 1

* Pair Programming practice
* Writing tests

Fetch the github repo

```
$ git clone https://github.com/standage/snds-demo.git
$ cd snds-demo
$ emacs snd
```

Original python script

**Fixed Script**

```
#! /usr/bin/env python
# Auth: Jennifer Chang, Sayali Kedari
# Date: 2018/07/16

def sums(values):
    """
    Given a list of numbers `values`, return a list of the sums of each non-
    decreasing sub-list. For example, if `values = [1, 2, 3, 3, 1, 5, 6, 3, 1,
    2, 3]`, the output should be `[9, 12, 3, 6]`.
    """
    s = values[0]
    out = []    
    for i in range(len(values) - 1):
#        print(values[i])
        if(values[i + 1] >= values[i]):
          s += values[i + 1]
        else:
          out.append(s)
          s = values[i + 1]
    out.append(s)
    return out

def main():
    values = [1, 2, 3, 3, 1, 5, 6, 3, 1, 2, 3]
    out = sums(values)
    print("input: ",values)
    print("output: ",out)
    print("valid: ",out == [9, 12, 3, 6])

if __name__ == '__main__' : main()
```

**How to run**

```
$ python snds.py 
input:  [1, 2, 3, 3, 1, 5, 6, 3, 1, 2, 3]
output:  [9, 12, 3, 6]
valid:  True
```