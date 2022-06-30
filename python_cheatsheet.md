# Python

# f-strings

Padding	            Expression

0 Padding	        {variable:0N}       `f'{1:05}' --> 00005`
Decimal Places	    {variable:.Nf}      `f'{1.2:.4f}' --> 1.2000`
Space Padding	    {variable:N}        `f'1{"abc":5}2'  --> 1abc  2`
Justified string	{variable:>N}       `f'1{"abc":>5}2' --> 1  abc2`
Date Formatting	    {date : Directive}  `f'{datetime.now():%A, %B %d, %Y}' --> Saturday, October 12, 1991.`

## f-string examples

```python
'\n'.join(f'{i: 3} lorem' for i in range(9,12))
#  9 lorem
# 10 lorem
# 11 lorem 

'\n'.join(f'ipsum:{i*0.7531: 5.2f}' for i in range(9,12))
# ipsum: 6.78
# ipsum: 7.53
# ipsum: 8.28
```

# argparse template

```python
import argparse

parser = argparse.ArgumentParser()
parser.add_argument("--name")
args = parser.parse_args()

# Name is now an attribute of args, and was set by 
# calling the script `python main.py --name myname
assert hasattr(args, 'name')
assert args.name == 'myname'
```

## The `add_argument()` method
https://docs.python.org/3/library/argparse.html

```python
parser.add_argument(
    args, # `"--name", "-n"`, etc. All these named parameters will be the same value in the end
    kwargs, # add_arguments takes many kwargs, none of which are documented in the function
        action,
        choices=[
            'store', #default, stores a value
            'store_const', 
            'store_true', #Stores a `True`-value. Good for creating flags
            'store_false',
            'append',
            'append_const',
            'count',
            'extend'
        ],
        default, #Default value, if none is passed when calling the script
        dest, #Name of the variable where argument values will be stored
        help, #Help text displayed when calling `python script.py --help`
        type, #Type of the value, fx `int`, `float`, etc.
)
```