# How lambda works.

Copy the code and execute in the terminal on the side.

For example, a very simple function (def) like the one below:

    def identity(x):
        return x + 1


It can be written this way::

    lambda x: x + 1

Let's compare the results:

    def identity(x):
        return x + 1

    print(identity(5))

The same result can be obtained with the use of Lambda, as below:

    print((lambda x: x + 1)(5))

Lambda can also receive more than one input parameter:

    print((lambda x, y: x + y)(2, 3))
