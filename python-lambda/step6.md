# Use of lambda in Lists:

Copy the code and execute in the terminal on the side.

## Conditions within Lambda:

If they are simple conditions, it is also possible to have it inside Lambda, it is worth remembering that if it is something more complex, it is more viable to create a function:

Syntax:

    lambda <arguments> : <Return Value if condition is True> if <condition> else <Return Value if condition is False>


Examples:

    print(list(map((lambda element: 0 if element is 4 else element), [1, 2, 3, 4, 5])))

    print(list(filter(lambda element: False if element is 4 else True, [1, 2, 3, 4, 5])))

    print(list(filter(lambda element: element is not 4, [1, 2, 3, 4, 5])))

    print(list(filter(lambda element: 3 < element < 5, [1, 2, 3, 4, 5])))
