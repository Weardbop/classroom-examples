# Functions Practice
Create complete the following functions as described in the Doc Strings. Annotate the function's parameters and return type. For example:
```python
def some_function(n: int, string: str) -> str:
    """Does something.
    
    Args:
        n (int): Some number.
        string (str): Some string
       
    Returns:
        str: A vague string.
    """
```

**Also**, for each function. Think of three test cases. For now, just call the function and expect a result, like we see in codingbat. 
For example if your function is called add and it adds three numbers the tests would look like:
```
add(5, 6, 7) -> 18
add(0, 0, 0) -> 0
add(1, 2, 3) -> 5
```

## The Functions
```python
from typing import List


def add(a: float, b: float) -> float: 
    """Adds two numbers.
    
    Args:
        a (float): A number.
        b (float): Another number.
    
    Returns:
        float: The sum of the two numbers.
    """
    return a+b
assert add(4, -1) == 3
assert add(144, 121) == 265
assert add(17, 200) == 217

def format_name(firstname: str, lastname: str) -> str:
    """Formats a name in 'Last, First' format.

    For example: "Smith, John"

    Args:
        first (str): The first name.
        last (str): The last name.
    
    Returns:
        str: The formatted name.
    """
    return lastname + ", " + firstname
assert format_name('Richard', 'Yang') == "Yang, Richard"
assert format_name('Matthieu', 'Tsang') == "Tsang, Matthieu"
assert format_name('Timothy', 'Shen') == "Shen, Timothy"

def strip_phone_number(unformattednumber: str)->str:
    """Remove all characters but integers from a phone number.

    Numbers entered by users can be given in a variety of formats.
    For example a user may enter their number as 901234567, or 905.123.4567 or
    (905)123-4567 or 905 123 4567. A database system should store numbers in a
    consistent format.

    The format we are looking for is just digits. E.g., 9051234567.

    Args:
        phone_number (str): A user-entered phone number in need of re-formatting.
    
    Returns:
        str: The phone number stripped to just it's digits.
    """
    numbers = ['0','1','2','3','4','5','6','7','8','9']
    formattednumber = ''
    for i in unformattednumber:
        if i in numbers:
            formattednumber += i
    return formattednumber
assert strip_phone_number("984-123-3241") == "9841233241"
assert strip_phone_number("(823)-123-0a29asd3asd") == "8231230293"
assert strip_phone_number("933 394 0123") == "9333940123"

def format_phone_number(unformattednumber: str) -> str:
    """Formats a phone number to (000)000-0000.

    Args:
        phone_number (str): A 10 digit phone number as a string.
            For example: "9051234567"
    
    Returns:
        str: The formatted phone number.
    """
    return '(' + unformattednumber[:3] + ')' + unformattednumber[3:6] + '-' + unformattednumber[6:]
assert format_phone_number('9051234567') == "(905)123-4567"
assert format_phone_number('0000000000') == '(000)000-0000'
assert format_phone_number('4236958098') == '(423)695-8098'

def add_from_list(numlist: list, index1: int, index2: int)->int:
    """Adds two values from a list at index a and b.
    
    Args:
        numbers (List[int]): a list of numbers.
        a (int): the first index location.
        b (int): the second index location.

    Returns:
        int: The two values at index a and b added together.
    """
    return numlist[index1] + numlist[index2]
assert add_from_list([7,6,4,23,5],2,4) == 9
assert add_from_list([6,9,2,1,4,2],0,-1) == 8
assert add_from_list([0,1,3,4,12,4],1,1) == 2
```
