# CMPS 2200  Recitation 01

**Name (Team Member 1):**Sofia Dellarosa  
**Name (Team Member 2):**Jaimie Morris

In this recitation, we will investigate asymptotic complexity. Additionally, we will get familiar with the various technologies we'll use for collaborative coding.

To complete this recitation, follow the instructions in this document. Some of your answers will go in this file, and others will require you to edit `main.py`. All tests are in `test_main.py`.

## Install Python Dependency

We need Python library of "tabulate" to visualize the results in a good shape. Please install it by running 'pip install tabulate' or 'pip install -r requirements.txt' in Shell Tab of Repl.  

## Running and testing your code

- To run tests, from the command-line shell, you can run
  + `pytest test_main.py` will run all tests
  + `pytest test_main.py::test_one` will just run `test_one`
  + We recommend running one test at a time as you are debugging.

## Turning in your work

- Once complete, click on the "Git" icon in the left pane on repl.it.
- Enter a commit message in the "what did you change?" text box
- Click "commit and push." This will push your code to your github repository.
- Although you are working as a team, please have each team member submit the same code to their repository. One person can copy the code to their repl.it and submit it from there.

## Comparing search algorithms

We'll compare the running times of `linear_search` and `binary_search` empirically.

`Binary Search`: Search a sorted array by repeatedly dividing the search interval in half. Begin with an interval covering the whole array. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise, narrow it to the upper half. Repeatedly check until the value is found or the interval is empty.

- [x] 1. In `main.py`, the implementation of `linear_search` is already complete. Your task is to implement `binary_search`. Implement a recursive solution using the helper function `_binary_search`. 

- [x] 2. Test that your function is correct by calling from the command-line `pytest test_main.py::test_binary_search`

- [ ] 3. Write at least two additional test cases in `test_binary_search` and confirm they pass.

- [x] 4. Describe the worst case input value of `key` for `linear_search`? for `binary_search`?

The worst case input value for "key" in linear is the last element in the array. The worst case input value for binary_search is if the key is the smallest or largest in the array.

**TODO: your answer goes here**

- [x] 5. Describe the best case input value of `key` for `linear_search`? for `binary_search`?
       For linear search, the best case value of 'key' would be the element at index 0 in myList. This would be O(1). For Binary search, the best case 'key' would be the middle index value. This would also be O(1).

**TODO: your answer goes here**

- [x] 6. Complete the `time_search` function to compute the running time of a search function. Note that this is an example of a "higher order" function, since one of its parameters is another function.

- [x] 7. Complete the `compare_search` function to compare the running times of linear search and binary search. Confirm the implementation by running `pytest test_main.py::test_compare_search`, which contains some simple checks.

- [x] 8. Call `print_results(compare_search())` and paste the results here:
      
      |        n |   linear |   binary |
      |----------|----------|----------|
      |       10 |    0.003 |    0.004 |
      |      100 |    0.005 |    0.003 |
      |     1000 |    0.245 |    0.012 |
      |    10000 |    0.809 |    0.024 |
      |   100000 |   11.188 |    0.038 |
      |  1000000 |  311.826 |    0.061 |
      | 10000000 | 2670.063 |    0.086 |

**TODO: add your timing results here**

- [x] 9. The theoretical worst-case running time of linear search is $O(n)$ and binary search is $O(log_2(n))$. Do these theoretical running times match your empirical results? Why or why not?
They do match. Linear search gets exponentially slower while n increases while in the binary search results the speed is increasing but very minimally. This is why binary search is preferred for larger data sets.

**TODO: your answer goes here**

- [ ] 10. Binary search assumes the input list is already sorted. Assume it takes $\Theta(n^2)$ time to sort a list of length $n$. Suppose you know ahead of time that you will search the same list $k$ times. 
  + What is worst-case complexity of searching a list of $n$ elements $k$ times using linear search? **TODO: your answer goes here**
  + For binary search? **TODO: your answer goes here**
     The worst case complexity for searching a list of n items k times using linear search would just be O(k*n) because each search takes O(n) time and it is searched k times.
    For binary search we have to do the same thing by searching k times for a search that is O(logn) so we get O(k*logn). Since we are sorting first we have to add O(n^2). So the worst case complexity would be O(n^2 + k*log(n))

  + For what values of $k$ is it more efficient to first sort and then use binary search versus just using linear search without sorting? **TODO: your answer goes here**
      + it is more efficient to first sort then use binary search for values if you are looking for more than one element (if you are running the search multiple times). Linear search is usually faster than binary search for small arrays. Alternatively, binary search is much more efficient for searching large arrays. 

