# Use of lambda in Lists:

Copy the code and execute in the terminal on the side.

## Reduce:
Apply function of two arguments cumulatively to the items of sequence, from left to right, so as to reduce the sequence to a single value. The left argument, x, is the accumulated value and the right argument, y, is the update value from the sequence. If the optional initializer is present, it is placed before the items of the sequence in the calculation, and serves as a default when the sequence is empty. If initializer is not given and sequence contains only one item, the first item is returned.

Syntax:

    reduce(function, iterables [,initializer])

    Parameter 	Description
    function 	Required. The function to execute for each item
    iterable 	Required. A sequence, collection or an iterator object. 
    initializer     Optional. Value placed before the iterable; default value if iterable is empty.


Reduce always works with 2 elements at a time. In the first iteration it is the first with the second item in the list, the following iterations are always the result of the last iteration plus the next item on the list:

Example:

    lst_Numbers = [3, 6, 10, 15, 20]

    print(functools.reduce(lambda a, b: a + b, lis))
    
This will produce the operations above:

    ((((3 + 6) + 10) + 15) + 20)

    Or

    3 + 6 = 9
    9 + 10 = 19
    19 + 15 = 34
    34 + 20 = 54

Translating to a simple way in functions, a reduce that adds the items in the list, as in the example above, would be something like this:


    def list_Sum(lst_Param):
        sum_Items = 0
        for item in lst_Param:
            sum_Items += item
        return sum_Items
    
    lst_Numbers = [3, 6, 10, 15, 20]

    print(list_Sum(lst_Numbers))

##Important:

Reduce, unlike Map, Filter and Sorted. It's in the module functools:

    import functools
    import operator

For understanding, the same action, using reduce, but still without lambda:


    def reduce_Sum(first_item, second_item):
        return first_item + second_item
    
    lst_Numbers = [3, 6, 10, 15, 20]
    
    print(functools.reduce(reduce_Sum, lst_Numbers))



The same result can be obtained with the use of Lambda, as below:

    lst_Numbers = [3, 6, 10, 15, 20]    

    print(functools.reduce(lambda a, b: a + b, lst_Numbers))


Using reduce to compute maximum element from list

    lst_Numbers = [3, 6, 10, 15, 20]

    print(functools.reduce(lambda a, b: a if a > b else b, lst_Numbers))

The Initializer can be used as a starting value for the operation, examples:

    lst_Numbers = [3, 6, 10, 15, 20]
    
    print(functools.reduce(lambda a, b: a + b, lst_Numbers, 100))
    print(functools.reduce(lambda a, b: a if a > b else b, lst_Numbers, 54))
    print(functools.reduce(lambda a, b: a + " " + b, ["Python", "for", "geeks"], ">_ "))
