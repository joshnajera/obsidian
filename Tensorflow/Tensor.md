What are they?
Genereally speaking, a vector , or array.  

Shape:
Represents the dimension(s) of data

## Creation
string_tensor = tf.Variable("This is a string", tf.string)
int_tensor = tf.Variable(324, tf.int16)
float_tensor = tf.Variable(3.14, tf.float64)

## Types
They can be 
- Variable  
- Constant (immutable)
- Placeholder (immutable)
- SparseTensor (immutable)


## Rank/Degree of tensors
Number of dimensions involved w a tensor.   Rank 0  iis also known as a scalar
Think of rank link the degree of nesting, the bigger it is, the deeper you're nested.

## Shape
Describes the number of elements in each rank

``` python
t1 = tf.ones([1,2,3])
t2 = rf.reshapre(t1, [2,3,1]) # So long as the multiplication of these numbers are the same, the reshape should be safe?
```



# Other

ones
``` python
tf.ones([1,2,3])
```
random

``` python
tf.random.normal([1,2,3]) # noarmally distributed
```