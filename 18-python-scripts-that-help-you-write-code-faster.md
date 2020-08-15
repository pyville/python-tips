## 서론

[원문 (영어)](https://morioh.com/p/4f4b74ba17cc?f=5c21fb01c16e2556b555ab32&fbclid=IwAR3K8fTbKsMhjJOLANsUhUIKX6Vwz9Uc-6JHSFbm3Vpv9XOAYIhjv8EO_ys "reference")

`Python`은 새내기용 프로그래밍 언어입니다. 가독성과 단순한 디자인이 바로 그 엄청난 인기의 원인이죠.

따라서 자주 쓰이는 `Python` 요령을 기억하고 있다면 당신의 코드 디자인을 개선할 수 있게 됩니다.

이걸 기억하고 있다면 매번 코딩을 할 때마다 구글링의 늪에서 헤엄치는 곤란을 겪지 않아도 되겠죠.

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

우리는 문자열의 `title()` 메서드를 이용하겠습니다.

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

문자열의 `join()` 메서드를 문자열의 리스트를 입력받아 하나의 문자열로 합치는 기능을 합니다.

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

문자열의 `split()` 메서드를 이용하여 문자열을 부분 문자열의 리스트로 쪼갤 수 있습니다.

`split()` 메서드의 매개 변수로 원하는 구분자를 넣어서 쪼갤 수도 있습니다.

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

조건제시법(List Comprehension)은 다른 리스트를 통해 리스트를 만드는 세련된 방법을 제공합니다.

아래의 코드 조각은 기존 리스트의 모든 원소에 각각 2를 곱하여 새로운 리스트를 만드는 예시입니다.

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

영어의 회문은 물론, 한국어의 회문 '토마토', '기러기', '스위스' 등도 판별할 수 있습니다.

```
my_string = "abcba"

if my_string == my_string[::-1]:
    print("palindrome")
else:
    print("not palindrome")

# Output
# palindrome
```

## 10. 인덱스와 값을 쌍으로 만들기

아래의 코드 조각은 `enumerate` 메서드를 이용하여 리스트의 각 항목의 인덱스와 값을 열거하는 예시입니다.

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

## 11. 아나그램 찾기

아나그램 찾기는 `Counter` 클래스를 응용하는 흥미로운 방법입니다.

아나그램(anagram)은 다른 단어나 구의 순서를 바꿔서 만들어진 단어나 구입니다.

소설 `해리 포터`의 유명한 대사인 "나는 볼드모트 경이다(I am Lord Voldemort)"는

사실 볼드모트의 본명인 "톰 마블로 리들(Tom Marvolo Riddle)"의 아나그램이죠.

거두절미하고, 문자열의 `Counter` 객체가 서로 동일하다면 서로 아나그램 관계가 됩니다.

```
from collections import Counter

str_1, str_2, str_3 = "acbde", "abced", "abcda"
cnt_1, cnt_2, cnt_3  = Counter(str_1), Counter(str_2), Counter(str_3)

if cnt_1 == cnt_2:
    print('1과 2는 아나그램 관계')
if cnt_1 == cnt_3:
    print('1과 3은 아나그램 관계')
```

## 12. try-except-else 블록 사용하기

`Python`의 예외 처리는 `try/except` 블록을 사용하여 쉽게 구현할 수 있습니다. 

예외가 발생하지 않았을 때 실행되는 `else` 블록을 추가하는 것도 유용하죠. 

예외에 상관없이 실행되어야 하는 코드는 `finally` 블록에 넣어 줍니다.

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

## 13. 리스트의 각 항목의 빈도

리스트의 각 항목의 빈도를 계산하는 여러 가지 방법이 있지만, 저는 `Counter` 클래스를 이용하는 방법을 선호합니다.

`Python`의 `counter`는 리스트, 딕셔너리 등에서 특정 항목의 등장 빈도를 기록하죠. 

`Counter()` 메서드를 호출하면 항목(key)과 등장 빈도(value)의 쌍으로 된 딕셔너리를 얻을 수 있습니다.

또한 `most_common(n)` 메서드는 등장 빈도가 제일 높은 항목을 n개 반환합니다.

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

## 14. 객체의 메모리 점유율 확인

아래 코드 조각은 `Python`에서 객체의 메모리 점유율을 확인하는 예시입니다. 

[더 알아보기](https://code.tutsplus.com/tutorials/understand-how-much-memory-your-python-objects-use--cms-25609 "Read More")

```
import sys

num = 21

print(sys.getsizeof(num))

# Python 2에서는 24
# Python 3에서는 28
```

## 15. 리스트에서 무작위 추출

아래 코드 조각은 `random` 모듈을 이용하여 리스트에서 n개의 항목을 무작위 추출하는 예시입니다.

```
import random

my_list = ['a', 'b', 'c', 'd', 'e']
num_samples = 2

samples = random.sample(my_list,num_samples)
print(samples)
# [ 'a', 'e'] 등 2개의 항목이 무작위로 추출됨
```

`secrets` 라이브러리를 사용하면 암호화된 무작위 추출이 가능합니다. 아래 코드 조각은 `Python 3`에서만 동작합니다.

```
import secrets                              # 보안 모듈 임포트
secure_random = secrets.SystemRandom()      # 안전한 random 객체 생성

my_list = ['a','b','c','d','e']
num_samples = 2

samples = secure_random.sample(my_list, num_samples)

print(samples)
# [ 'e', 'd'] 등 2개의 항목이 무작위로 추출됨
```

## 16. 코드 실행 시 소요 시간 측정

아래 코드 조각은 `time` 라이브러리를 이용해 특정 코드 조각을 실행하는 데 소요되는 시간을 측정합니다.

```
import time

start_time = time.time()
# Code to check follows
a, b = 1,2
c = a+ b
# Code to check ends
end_time = time.time()
time_taken_in_micro = (end_time- start_time)*(10**6)

print("소요 시간: {0} ms").format(time_taken_in_micro)
```

## 17. 리스트의 중첩 문제 해결

잘 아시다시피 `Python`에서는 리스트 안에 리스트를 넣어서 중첩된 리스트를 만들 수 있습니다.

하지만 리스트가 얼마나 중첩되어 있는지 알기 어려울 때, 리스트의 원소들을 1차원으로 줄일 수 있습니다.

```
from iteration_utilities import deepflatten

# 리스트가 한 번만 중첩되어 있을 때(2차원), 다음 코드를 사용할 수 있습니다.
def flatten(l):
  return [item for sublist in l for item in sublist]

l = [[1,2,3],[3]]
print(flatten(l))
# [1, 2, 3, 3]

# 리스트가 얼마나 중첩되어 있는지 알 수 없을 때, 다음 라이브러리 메서드를 사용합니다.
l = [[1,2,3],[4,[5],[6,7]],[8,[9,[10]]]]

print(list(deepflatten(l, depth=3)))
# [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

적절한 형식으로 포맷된 배열을 원한다면, [Numpy flatten](https://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.flatten.htmlhttps://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.flatten.html "reference")이 더 적합합니다.


## 18. 두 딕셔너리 병합하기

`Python 2`에서는 `update()` 메서드를 통해 딕셔너리를 병합했습니다.

`Python 3.5` 에서는 더 간단한 방법을 제공하죠.

아래 코드 조각은 두 딕셔너리를 병합하는 예시입니다. 

두 딕셔너리에 동일한 항목이 존재할 경우, `dict_2`의 값이 적용됩니다.

```
dict_1 = {'apple': 9, 'banana': 6}
dict_2 = {'banana': 4, 'orange': 8}

combined_dict = {**dict_1, **dict_2}

print(combined_dict)
# 출력
# {'apple': 9, 'banana': 4, 'orange': 8}
```

여기까지 읽어주셔서 감사합니다.

번역: 이정주
