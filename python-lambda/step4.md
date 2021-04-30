# Use of lambda in Lists:

Copy the code and execute in the terminal on the side.

## Filter:

The filter() function returns an iterator were the items are filtered through a function to test if the item is accepted or not.

Syntax

    filter(function, iterable)

    Parameter 	Description
    function 	A Function to be run for each item in the iterable
    iterable 	The iterable to be filtered


The filter () must receive as a parameter a list with the same number of items as the original list, but only with True and False.
Example:

In the list [1, 2, 3, 4, 5], if we do not want item "4" to appear, we must have something that returns for each item on the list [True, True, True, False, True]

Example: (We will see Conditions if..else .. in lambda later)

What would it be like if we were to use a function:


    def fn_FilterNumbers(element):
        if element is 4:
            return False
        else:
            return True

    print(list(filter(fn_FilterNumbers, [1, 2, 3, 4, 5])))


With lambda, it can be written this way:

    print(list(filter(lambda element: False if element is 4 else True, [1, 2, 3, 4, 5])))

Another example:

    lst_Itens = ["Item-0", "Item-1", "Item-2", 'Item-3', 'Item-4', 'Item-5', 'Option-1', 'Option-2', 'Option-3']

    print(list(map(lambda element: True if element[:6] == 'Option' else False, lst_Itens)))

    print(list(filter(lambda element: True if element[:6] == 'Option' else False, lst_Itens)))
