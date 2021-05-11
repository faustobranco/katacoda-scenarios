# Use of lambda in Lists:

Copy the code and execute in the terminal on the side.


Lambda is normally used in lists from some other function, for example the most common ones: map, filter, reduce or sorted.


## Maps:
The iterable to the map() function can be a dictionary, a list, etc. The map() function basically maps every item in the input iterable to the corresponding item in the output iterable, according to the logic defined by the lambda function

Syntax:

    map(function, iterables)

    Parameter 	Description
    function 	Required. The function to execute for each item
    iterable 	Required. A sequence, collection or an iterator object. You can send as many iterables as you like, just make sure the function has one parameter for each iterable.

Once again, let's show the usage example, with a function and compare it with Lambda:

    def identity(x):
        return x + 1

    print(list(map(identity, [1, 2, 3, 4, 5])))


The same result can be obtained with the use of Lambda, as below:

    print(list(map(lambda x: x + 1, [1, 2, 3, 4, 5])))


Example of lambda iteration with two lists argument entries:

    print(list(map(lambda x, y: x - y, [2, 4, 6], [1, 3, 5])))