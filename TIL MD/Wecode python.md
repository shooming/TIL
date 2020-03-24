# Python

## print
```python
print("hello world!")
```
print 명령어 는 화면에 내용을 출력하기 위해 사용한다.

print는 함수 이름이며 따옴표("")안에 들어가는 내용은 string이라고 부른다.

------

## Data Types
Data Type은 작성된 내용이 숫자인지 텍스트인지를 의미하며 몇 가지 타입들이 존재한다.

1. ### Integer
    정수값(int라고도 함), 1,2,3 과 같이 일상적으로 사용되는 숫자
2. ### Float
    실수값으로 소수점이 있는 숫자 2.0, 5.99
3. ### Complex Numbers
    복소수를 이야기하며 5+6j와 같이 표현 수학에서는 i지만, 전기,전자 공학에서의 복소수는 j로 표기한다(i가 먼저 사용되어 겹치는 경우가 많기 때문 ex : 전류(i))
4. ### string
    기본적인 문자열
5. ### Boolean
    Bool이라고도 하며 조건문(condition)에 주로 사용 True / False 참과 거짓을 나타낸다.
    
        0               = False
        0이 아닌 숫자    = True
        777 == 777        True
        777 == "777"      False (따옴표안에 표현되어 string type이기 때문)

------

## Math Expression
몇 가지 기호를 통해 기본적인 수학 연산들이 가능하다.

```python
10 + 10 = 20    ## 더하기 연산자 "+"
20 - 20 = 0     ## 빼기 연산자   "-"
30 * 30 = 900   ## 곱하기 연산자 "*"
2 ** 3  = 8     ## 거듭제곱 연산자 "**"
40 / 40 = 1     ## 나누기 연산자 "/"
7 // 3 = 2      ## 정수 나누기   "//"
10 % 3 = 1      ## 나머지 연산자 "%"
```
위의 연산자들 사용 할 수 있다.

다른 연산자들은 소숫점 계산을 하지 않으면 int형이 출력될 가능성이 높지만 나누기는 int형으로 서로 나누더라도 소숫점이 나올 수 있으므로 기본 float형으로 값이 출력된다.

## Advanced Math Expressions
```python
num1 = 10

num1 += 1   ## num1 = 11 
num1 -= 1   ## num1 = 9 
num1 *= 2   ## num1 = 20
num1 /= 5   ## num1 = 2
```
위의 예제는 각각의 연산에 num1이 10 그대로 반영됨을 전제로 한다. 그대로 사용시 연속적인 연산이된다.

위 계산들은 num1을 계산 후 다시 num1으로 값을 저장하는 연산자이다.

    num1 += 1   ==  num1 = num1 + 1
    num1 -= 1   ==  num1 = num1 - 1
    num1 *= 2   ==  num1 = num1 * 2
    num1 /= 5   ==  num1 = num1 / 5
위와 같이 축약시켜 놓은 것이다.

이러한 연산을 하는 이유는 반복되는 연산을 수행하기 위해서이다. ex) 방문자수 카운터

------

## Order of Operators
수학에서도 곱셈이 덧셈보다 먼저 계산되듯 python 연산자도 연산순위가 존재한다.

일단 간단하게 기본적인 연산자만 보면
```bash
(우선순위 낮음) + , - <<< *, /, % <<< ** <<< ( ) (우선순위 높음)
```
위와 같은 순서가 된다.

------

## Concatenating Text Strings
문자열도 더할 수 있다.
```python
print("안녕하세요")
print("안녕" + "하세요")
```
그러므로 위의 예제의 두 print의 문자열은 더해져서 같은 출력값이 나오게 된다.

```python
hey = "하세요"
print("안녕" + hey)
```
위와 같이 함수도 더할 수 있다
단 문자열은 문자열끼리만 덧셈이 가능하다.

복잡한 string concatenation
python에는 문자열에 변수를 넣는 몇가지 방법이 존재한다.

```python
a = 10
b= "hi"

print("%s, 나는 %d살이야" %(a,b))

print("{0}, 나는 {1}살이야" .format(a,b))


name = input() 

print(f"Hello, {name}")
```
위와 같이 3가지 정도 존재하며

첫번째 print는 %-formatting이고 %뒤에 s, d 등으로 데이터 타입을 표시해서 값이 넣어준다.

두번째 print는 .format()함수를 이용한 방법이다. 중괄호에 숫자를 써놓으면 포맷팅 순서대로 숫자가 매겨져 있는데 해당 하는 숫자에 값이 들어감 만약 비어있을 경우 순서대로 들어감

세번째 print는 f-string라는 방식이다. 해당 방식은 문자열(")앞에 f를 적고 원하는 값을 넣을 자리에 중괄호를 넣고 변수를 집어 넣으면 된다.

------

## Comparison Operators
python문에는 몇가지 비교연산자가 있다
```python
A == A  ## A는 A와 같은가
A != B  ## A는 B와 다른가
A > B   ## A는 B보다 큰가
A < B ## A는 B보다 작은가
A >= B ## A는 B보다 크거나 같나
A <= B ## A는 B보다 작거나 같은가
```
비교연산자들의 기준은 `오른쪽`에 있는 내용이며 `왼쪽`에 값을 넣어서 오른쪽과 비교하여 True, False를 판별한다.

------

## IF
```Python
if 조건문:
    조건문 True 일 경우 출력
```
조건문이 일치하면 바로아래 들여쓰기되어 해당 함수에 종속된 내용들이 실행된다.

## elif, else

------

## 논리 연산자
```python
if A == 1 and B == 1:
    A와 B 값의 비교연산이 둘다 True가 되어야 출력됨

if A == 1 or B == 1:
    A와 B 값의 비교연산 중 둘중 하나만 True가 되어도 출력됨

if (A == 1 or B == 3) and (A == 1 and B == 1:)
    and 와 or 연산자는 복합적인 사용도 가능하다
```
아래 표를 확인하면 간단하게 알 수 있다
|   A   |   B   |  and  |
|:-----:|:-----:|:-----:|
| False | False | False |
| False |  Ture | False |
|  Ture | False | False |
|  Ture |  Ture |  Ture |

|   A   |   B   |   or  |
|:-----:|:-----:|:-----:|
| False | False | False |
| False |  Ture |  Ture |
|  Ture | False |  Ture |
|  Ture |  Ture |  Ture |

------

## commnet
```python
# 주석을 달고 싶은 문장에 #을 작성하면된다 한줄 주석에 사용한다.

'''
여러 줄
주석 처리
'''

"""
여러 줄
주석 처리
"""
```
주석은 사실 # 하나만이 주석이라 볼 수 있다.
"""
"""
이나
'''
'''
은 사실 multiline을 처리할수 있게 해주는 장치이다
실제로는 문자열화되었지만 출력되지 않았기때문에 정확히는 주석이 아니지만 여러줄 주석처럼 활용한다.

------

## Function
함수는 일정한 작업을 수행하는 코드블럭으로 자주 사용되는 코드들을 함수로 만들어 효과적으로 사용한다. 또한 함수로 정리해 코드의 가독성을 높인다.

input은 parameter
output은 return 값 이라고 한다.

```python
def 함수명(parameter):
    문장1
    문장2
    ...
    문장N
    [return 리턴값]
```
함수는 위와 같은 형태로 작성을 하며 parameter와 return 은 옵션이므로 parameter와 return이 없는 함수도 존재한다.

------

## Function Parameters

### positional arguments
```python
def like_food(food1, food2):
    print(f"{food1}과{food2}를 좋아한다.")

like_food("치킨","피자") # food1 = 치킨 / food2 = 피자

## "치킨과 피자를 좋아한다"가 출력됨
```
위와 같이 function에 바로 parameter값을 바로 넣어서 전달하면서 호출하는 형태이며 넣은 순서대로 들어간다.

### Keyword Arguments
```python
def like_food(food1, food2):
    print(f"{food1}과{food2}를 좋아한다.")

like_food(food2="피자",food1="치킨") # food1 = 치킨 / food2 = 피자

## "치킨과 피자를 좋아한다"가 출력됨
```
parameter 이름으로 맞추어서 값을 전해줄 수 있습니다. 이를 keyword argments 방식이라고 함 전달되는 parameter의 이름과 맞으면 순서는 바뀌어도 상관없이 전달된다.

### Mixing positional arguments and keyword arguments
```python
def like_food(food1, food2):
    print(f"{food1}과{food2}를 좋아한다.")

like_food("치킨",food2="피자") # food1 = 치킨 / food2 = 피자

## "치킨과 피자를 좋아한다"가 출력됨
```
해당 방식은 positional arguments와 keyword arguments를 합쳐서 사용한 방법이다. 이때 keyword arguments는 순서가 바뀌어도 전달되는 parameter의 이름이 지정되어 있어 문제가 없지만 positional arguments는 parmeter 이름이 지정되지 않아 함수값을 전달할때 위치에 해당하는 parameter의 이름으로 보내기 때문에 순서가 틀려버리면 에러가 발생되어 버린다.
```python
def like_food(food1, food2):
    print(f"{food1}과{food2}를 좋아한다.")

like_food(food2="피자","치킨")
# 위의 값은 에러가 발생한다.
```
위의 값은 에러가 발생하는데
첫번째 값인 keyword arguments가 먼저나와서 food2에 피자가 전달되었는데 positional arguments인 치킨이 다시 food2위치에 들어가려하며 food1에는 아무런 값도 들어가지 않은 상태가 되어 에러가 발생하게된다.

### Parameter Default Value
Parameter가 전달되지 않았을때 default값을 출력하여 줄 수 있다.
```python
def like_food(food1, food2 = "피자"):
    print(f"{food1}과{food2}를 좋아한다.")

like_food("치킨") # food1 = 치킨 만 전달됨

## "치킨과 피자를 좋아한다"가 출력됨
```
like_food함수의 parameter전달시 피자를 전달 하지 않았지만 함수에 default 설정에 의해 자동으로 피자가 출력된다.

```python
def like_food(food1="치킨", food2):
    print(f"{food1}과{food2}를 좋아한다.")

like_food("피자") # 에러가 발생한다.
```
위와 같은 default value parameter는 에러가 발생하게 된다. 그 이유는 함수 parameter 전달시 생략하는 parameter가 food1인지 food2인지 알 수 없기 때문에 피자를 전달할때 positional arguments로 생각하면 food1의 위치이다 하지만 치킨이라는 값이 기본값으로 되어있다 하지만 food2에 parameter는 전달되지 않았다. 하지만 위치는 food1이다 그럼 food2로 보내야 하는가? 파이썬은 고민하게된다. 그래서 에초에 이런 문법을 사전에 차단하려고 하는것 같다. 그러므로 Default Value값을 뒤에 배치해야한다. 그리고 food2에도 기본값을 정의해 주어 둘다 default value를 가지면 에러가 발생하지 않는다.
like_food(food=2"피자")로 지정하여 보내도 `SyntaxError: non-default argument follows default argument`를 뱉어낸다.