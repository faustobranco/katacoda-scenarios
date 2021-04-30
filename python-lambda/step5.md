# Use of lambda in Lists:

Copy the code and execute in the terminal on the side.

## Sorted:

Sorted is no different:

The sorted() function returns a sorted list of the specified iterable object.

You can specify ascending or descending order. Strings are sorted alphabetically, and numbers are sorted numerically.
Syntax:
    sorted(iterable, key=key, reverse=reverse)

Parameter 	Description
iterable 	Required. The sequence to sort, list, dictionary, tuple etc.
key 	    Optional. A Function to execute to decide the order. Default is None
reverse 	Optional. A Boolean. False will sort ascending, True will sort descending. Default is False

What would it be like if we were to use a function:

    def fn_SortItens(element):
        return element[-1:] + element[:1]

    lst_Itens = ["Item-0", "Item-1", "Item-2", 'Item-3', 'Item-4', 'Item-5', 'Option-1', 'Option-2', 'Option-3']

    print(list(sorted(lst_Itens, key=fn_SortItens)))


With lambda, it can be written this way:
    lst_Itens = ["Item-0", "Item-1", "Item-2", 'Item-3', 'Item-4', 'Item-5', 'Option-1', 'Option-2', 'Option-3']

    print(list(sorted(lst_Itens, key=lambda element: element[-1:] + element[:1])))
