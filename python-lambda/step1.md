# How lambda works.


For example, a very simple function (def) like the one below:

`def identity(x):
    return x + 1
`{{execute}}

It can be written this way::

`lambda x: x + 1`{{execute}}

Let's compare the results:

`def identity(x):
    return x + 1`{{execute}}

`print(identity(5))`{{execute}}

The same result can be obtained with the use of Lambda, as below:

`print((lambda x: x + 1)(5))`{{execute}}

Lambda can also receive more than one input parameter:

`print((lambda x, y: x + y)(2, 3))`{{execute}}
