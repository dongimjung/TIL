## 1\. 파이썬 자료형(Data type)

 **1) 숫자형(Number)**

 **2) 숫자형(float)**

 **3) 문자형(String)**

 **4) 리스트형(List)** 

 - 개발자들이 변수를 관리하다보니 불편

 - 여러개의 변수를 한 곳에서 관리할 수 없을까?

 - \[변수, 변수, 변수\]

 **5) 튜플형(Tuple)**

 - (  ) 소괄호로 감싸져있다.

 - 한번 생성되면 값 변경이 불가능하다 => 요소를 더하거나, 제거하거나, 수정하거나 하는 것이 불가능.!!!!!

\- 좀 까다로운것같은데.. 왜 굳이 튜플을 사용할까? -> 적은 메모리를 사용하여 공간효율적이다!

 **6) 딕셔너리(Dict)**

 - {key1: value1, key2: value2} => json

 - API라고 불리는 형태와 동일 => FastAPI

 **7) 집합형(Set)**

 - 순서가 없다

 - 중복을 허용하지 않는다.

\- 일반적으로 데이터가 존재하는지 존재하지 않는지 여부만 판별하고자 할 때 많이 쓰인다!

 **8) 불형(Boolean)**

파이썬에서는아래처럼 문자와 숫자를 더했다가는 에러가 난다고 한다. 

name = 'inseop'

age = 30

print("Name : " + name +", Age: " + age)

따라서 적절히 포매팅을 해주어야 한다.

print("Name : " + name +", Age: " + str(age))

print("Name : {}, Age: {}".format(name, age)) \# format

print(f"Name : {name}, Age: {age}")

신기할 따름이다.

ex) 리스트형 예시

x = \['a', 'b', 'c', \['d', 'e'\]\]

ex) 튜플형 예시

a = (1,2,3,4,5)

  

\# a\[0\] = 10

\# a.append(10)

  

\# 그러면 a 라는 튜플을 내가 변형할 수 있는 방법은 없는걸까?

new\_a = a + (10, )

new\_a

ex) 집합형 예시

x = set(\[1,2,3,5,7,5,3,1,3,4,6,3\])

type(x)

  

x

```
{1, 2, 3, 4, 5, 6, 7}
```

## 2\. 제어문

**1) 조건문(if)**

**2) 반복문(for, while)**

ex) 조건문 예시

num = 5

  

if num == 5:

print("숫자가 5보다 작습니다.")

elif num == 10:

print("숫자가 10보다 작습니다.")

else:

print("숫자가 10보다 큽니다.")

ex) 반복문 예시

for i in range(2, 11):

print(i)

cities = \['seoul', 'daejeon', 'daegu', 'busan'\]

  

for city in cities:

if city == 'busan':

print("해운대를 가세요.")

a = 0

while a < 5:

\# a = a + 1

a += 1\. \# 이게 없으면 0 무한대로 찍히는 현상. 

print(a) 

## 3\. 함수

**1) 내장함수**

**2) 외장함수(import)**

**3) 내가 만든 함수(def)**

ex) 내가 만든 함수 예시

def my\_name(name, age): \# input

print(f"제 이름은 {name}, 나이는 {age} 입니다.") \# output: X

return name, age

  

output = my\_name('인섭', 30)

print(output) \# None -> 인섭

## 4\. 클래스

ex) 클래스 예시

class FishBread: \# Camel Case

\# 초기화 => 생성자 => 클래스가 호출됐을 때 가장 먼저 실행되는 함수(메소드)

def \_\_init\_\_(self, name, ingredient):

self.name = name

self.ingredient = ingredient

  

def bread(self):

print(f"붕어빵의 이름은 {self.name}, 재료는 {self.ingredient}")

  

redbean\_bread = FishBread('팥붕어빵', '팥')

  

redbean\_bread.name

redbean\_bread.ingredient

redbean\_bread.bread()

  
  

sucream\_bread = FishBread("슈크림 붕어빵", "슈크림")

sucream\_bread.name

sucream\_bread.ingredient

  

sucream\_bread.bread()

  

redbean\_bread \# 인스턴스(객체)

  

redbean\_bread.name

redbean\_bread.bread()

붕어빵의 이름은 팥붕어빵, 재료는 팥

붕어빵의 이름은 슈크림 붕어빵, 재료는 슈크림

붕어빵의 이름은 팥붕어빵, 재료는 팥

하루동안 나간 진도 치고 굉장히 타이트하다.

그럼에도 강사님이 중간중간 포인트를 잘 짚어주시고 이게 굳이 왜 필요한지, 왜 이런것이 나왔는지 설명해주시는 것을 보고 깊은 통찰력을 느꼈다.

학생들에 대한 기대수준이 높은 것 같아 정말 열심히 해야겠다는 생각이 들었다.

개인적인 사정으로 오후시간에 조퇴를 할 수밖에 없었는데, 너무나도 아쉽다. 특히 크롤링을 놓친것이..
