## 서론

[원문 (영어)](https://morioh.com/p/4f4b74ba17cc?f=5c21fb01c16e2556b555ab32&fbclid=IwAR3K8fTbKsMhjJOLANsUhUIKX6Vwz9Uc-6JHSFbm3Vpv9XOAYIhjv8EO_ys "reference")

`Python`은 새내기용 프로그래밍 언어입니다. 가독성과 단순한 디자인이 바로 그 엄청난 인기의 원인이죠.

따라서 자주 쓰이는 `Python` 요령을 기억하고 있다면 당신의 코드 디자인을 개선할 수 있게 됩니다.

이걸 기억하고 있다면 매번 코딩을 할 때마다 버그의 늪에서 헤엄치는 곤란을 겪지 않아도 되겠죠.

여기서 언급할 요령들은 당신의 '슬기로운 코딩생활'에 도움이 될 겁니다.

## 1. 문자열에서의 중복 제거

아래의 코드 조각은 문자열에서 중복을 제거하여 모든 유일한 문자를 찾는 예시입니다.

우리는 `Python`의 집합(set)이 [중복을 허용하지 않는다는 속성](https://medium.com/python-pandemonium/https-medium-com-python-pandemonium-an-introduction-to-python-sets-part-i-120974a713be "reference")을 이용하겠습니다.

```
my_string = "aavvccccddddeee"

# 문자열을 집합으로 변환하기
temp_set = set(my_string)

# join 메서드를 사용하여 집합을 문자열로 합치기
new_string = ''.join(temp_set)

print(new_string)
```

## 2. 단어의 첫 글자만 대문자로 만들기

아래의 코드 조각은 문자열을 첫 글자만 대문자로(Title Case) 변환하는 예시입니다.

우리는 문자열의 `title` 메서드를 이용하겠습니다.

```
my_string = "my name is chaitanya baweja"

# 문자열의 title 메서드 사용하기
new_string = my_string.title()

print(new_string)

# 출력
# My Name Is Chaitanya Baweja
```

## 3. 문자열 뒤집기

아래의 코드 조각은 `Python`의 슬라이스를 이용하여 문자열을 뒤집는 예시입니다.

 ```
 # 슬라이스로 문자열 뒤집기

my_string = "ABCDE"
reversed_string = my_string[::-1]

print(reversed_string)

# 출력
# EDCBA
 ```
 
[더 알아보기](https://medium.com/swlh/how-to-reverse-a-string-in-python-66fc4bbc7379 "more")

## 4. 문자열 또는 리스트를 정해진 횟수만큼 반복 출력하기

문자열 또는 리스트에서 곱하기(*) 기호를 사용하여 원하는 만큼 반복할 수 있습니다.

```
n = 3 # 반복 횟수

my_string = "abcd"
my_list = [1,2,3]

print(my_string*n)
# abcdabcdabcd

print(my_list*n)
# [1,2,3,1,2,3,1,2,3]
```

이 방법을 이용해서 0 등의 상수를 정해진 횟수만큼 가지는 리스트를 만들 수도 있습니다.

```
n = 4
my_list = [0]*n # n은 리스트의 크기
# [0, 0, 0, 0]
```

## 5. 문자열의 리스트를 하나의 문자열로 합치기

문자열의 `join` 메서드를 문자열의 리스트를 입력받아 하나의 문자열로 합치는 기능을 합니다.

쉼표(,)를 구분자로 한 예시입니다.

```
list_of_strings = ['My', 'name', 'is', 'Chaitanya', 'Baweja']

# 쉼표(,)를 구분자로 join 메서드 사용
print(','.join(list_of_strings))

# 출력
# My,name,is,Chaitanya,Baweja
```

## 6. 두 변수의 값을 교환하기

`Python`에서는 제3의 변수를 이용하지 않고도 매우 간편하게 두 변수의 값을 교환할 수 있습니다.

```
a = 1
b = 2

a, b = b, a

print(a) # 2
print(b) # 1
```

## 7. 문자열을 부분 문자열의 리스트로 쪼개기

We can split a string into a list of substrings using the .split() method in the string class. 

You can also pass as an argument the separator on which you wish to split.

```
string_1 = "My name is Chaitanya Baweja"
string_2 = "sample/ string 2"

# 기본 구분자 ' '
print(string_1.split())
# ['My', 'name', 'is', 'Chaitanya', 'Baweja']

# 구분자 '/'
print(string_2.split('/'))
# ['sample', ' string 2']
```

## 8. 조건제시법

조건제시법(List Comprehension) provides us with an elegant way of creating lists based on other lists.

The following snippet creates a new list by multiplying each element of the old list by two.

```
# 리스트의 모든 원소에 2를 곱하기

original_list = [1,2,3,4]

new_list = [2*x for x in original_list]

print(new_list)
# [2,4,6,8]
```

## 9. 회문 판별

우리는 이 글의 3번 항목에서 이미 문자열 뒤집기를 다뤘습니다.

따라서 `Python`에서 회문(palindrome, 거꾸로 해도 똑같은 문자열)을 판별하는 것 또한 직관적으로 가능하죠.

```
my_string = "abcba"

if my_string == my_string[::-1]:
    print("palindrome")
else:
    print("not palindrome")

# Output
# palindrome
```

## 10. Using Enumerate to Get Index/Value Pairs

The following script uses enumerate to iterate through values in a list along with their indices.

```
my_list = ['a', 'b', 'c', 'd', 'e']

for index, value in enumerate(my_list):
    print('{0}: {1}'.format(index, value))

# 0: a
# 1: b
# 2: c
# 3: d
# 4: e
```

## 11. Find Whether Two Strings are Anagrams

An interesting application of the Counter class is to find anagrams.

An anagram is a word or phrase formed by rearranging the letters of a different word or phrase.

If the Counter objects of two strings are equal, then they are anagrams.

```
from collections import Counter

str_1, str_2, str_3 = "acbde", "abced", "abcda"
cnt_1, cnt_2, cnt_3  = Counter(str_1), Counter(str_2), Counter(str_3)

if cnt_1 == cnt_2:
    print('1 and 2 anagram')
if cnt_1 == cnt_3:
    print('1 and 3 anagram')
```

## 12. Using the try-except-else Block

Error handling in Python can be done easily using the try/except block. 

Adding an else statement to this block might be useful. 

It’s run when there is no exception raised in the try block.

If you need to run something irrespective of exception, use finally.

```
a, b = 1,0

try:
    print(a/b)
    # b가 0일 때 0으로 나눌 수 없으므로 except문 실행
except ZeroDivisionError:
    print("오류: 0으로 나누기")
else:
    print("예외가 발생하지 않음")
finally:
    print("항상 실행되는 블록")
```

## 13. Frequency of Elements in a List

There are multiple ways of doing this, but my favorite is using the Python Counter class.

Python counter keeps track of the frequency of each element in the container. 

Counter() returns a dictionary with elements as keys and frequency as values.

We also use the most_common() function to get themost_frequentelement in the list.

```
# 리스트의 각 항목의 빈도 계산하기
from collections import Counter

my_list = ['a','a','b','b','b','c','d','d','d','d','d']
count = Counter(my_list) # Counter 객체 정의하기

print(count) # 모든 항목에 대해서
# Counter({'d': 5, 'b': 3, 'a': 2, 'c': 1})

print(count['b']) # 특정 항목에 대해서
# 3

print(count.most_common(1)) # 가장 자주 등장하는 항목
# [('d', 5)]
```

## 14. Check the Memory Usage of an Object

The following script can be used to check the memory usage of an object. 

[더 알아보기](https://code.tutsplus.com/tutorials/understand-how-much-memory-your-python-objects-use--cms-25609 "Read More")

```
import sys

num = 21

print(sys.getsizeof(num))

# In Python 2, 24
# In Python 3, 28
```

## 15. 리스트에서 무작위 추출

The following snippet generates n number of random samples from a given list using the random library.

```
import random

my_list = ['a', 'b', 'c', 'd', 'e']
num_samples = 2

samples = random.sample(my_list,num_samples)
print(samples)
# [ 'a', 'e'] this will have any 2 random values
```

I have been recommended the secrets library for generating random samples for cryptography purposes. 

The following snippet will work only on Python 3.

```
import secrets                              # imports secure module.
secure_random = secrets.SystemRandom()      # creates a secure random object.

my_list = ['a','b','c','d','e']
num_samples = 2

samples = secure_random.sample(my_list, num_samples)

print(samples)
# [ 'e', 'd'] this will have any 2 random values
```

## 16. Time Taken to Execute a Piece of Code

The following snippet uses the time library to calculate the time taken to execute a piece of code.

```
import time

start_time = time.time()
# Code to check follows
a, b = 1,2
c = a+ b
# Code to check ends
end_time = time.time()
time_taken_in_micro = (end_time- start_time)*(10**6)

print(" Time taken in micro_seconds: {0} ms").format(time_taken_in_micro)
```

## 17. Flattening a List of Lists

Sometimes you’re not sure about the nesting depth of your list, 

and you simply want all the elements in a single flat list.

```
from iteration_utilities import deepflatten

# if you only have one depth nested_list, use this
def flatten(l):
  return [item for sublist in l for item in sublist]

l = [[1,2,3],[3]]
print(flatten(l))
# [1, 2, 3, 3]

# if you don't know how deep the list is nested
l = [[1,2,3],[4,[5],[6,7]],[8,[9,[10]]]]

print(list(deepflatten(l, depth=3)))
# [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

적절한 형식으로 맞춰진 배열을 원한다면, [Numpy flatten](https://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.flatten.htmlhttps://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.flatten.html "reference")이 더 적합합니다.


## 18. Merging Two Dictionaries

While in Python 2, we used the update() method to merge two dictionaries; Python 3.5 made the process even simpler.

In the script given below, two dictionaries are merged. 

Values from the second dictionary are used in case of intersections.

```
dict_1 = {'apple': 9, 'banana': 6}
dict_2 = {'banana': 4, 'orange': 8}

combined_dict = {**dict_1, **dict_2}

print(combined_dict)
# Output
# {'apple': 9, 'banana': 4, 'orange': 8}
```

여기까지 읽어주셔서 감사합니다.

번역: 이정주
