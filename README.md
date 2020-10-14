# python_basic

<pre>
PI = 3.14


def input_radius():
    radius_str = input("반지름을 입력하세요: ")
    return float(radius_str)


def calc_circle_area(r):
    return PI * r * r


def calc_circumference(r):
    return 2 * PI * r


radius = input_radius()
circle_area = calc_circle_area(radius)
circumference = calc_circumference(radius)

print("원의 면적: {0:0.2F}, 원의 둘레: {1:0.2F}".format(circle_area, circumference))
</pre>

<pre>
if 문을 활용해 아래의 실행 결과를 반영한 간단 계산기를 만들어 봅시다. 
우리가 만들어 볼 간단 계산기는 사용자로부터 두 개의 숫자와 한 개의 연산자를 입력 받아 
그 연산자에 따른 계산을 수행할 것입니다. 
연산자는 +(덧셈), -(뺄셈), *(곱셈), /(나눗셈)을 지원하도록 합니다.

[ 실행 결과 1 ]
첫 번째 숫자를 입력하세요: 2 
연산자를 입력하세요 (+, -, *, /): + 
두 번째 숫자를 입력하세요: 3 
2 + 3 = 5

[ 실행 결과 2 ]
첫 번째 숫자를 입력하세요: 2 
연산자를 입력하세요 (+, -, *, /): # 
두 번째 숫자를 입력하세요: 3 
'#'는 본 프로그램에서 지원하지 않는 연산자입니다.

operand1, operator, operand2 = 0, "", 0

operand1 = int(input("첫 번째 숫자를 입력하세요: "))
operator = input("연산자를 입력하세요 (+, -, *, /): ")
operand2 = int(input("두 번째 숫자를 입력하세요: "))

if operator == "+":
    print("%d + %d = %d" % (operand1, operand2, operand1 + operand2))
elif operator == "-":
    print("%d - %d = %d" % (operand1, operand2, operand1 - operand2))
elif operator == "*":
    print("%d * %d = %d" % (operand1, operand2, operand1 * operand2))
elif operator == "/":
    print("%d / %d = %.2f" % (operand1, operand2, operand1 / operand2))
else:
    print("'%s'는 본 프로그램에서 지원하지 않는 연산자입니다" % operator)
</pre>

<pre>
다음 세 가지 결과의 패턴을 각각 분석해 for문과 while문과 같은 반복문을 이용한 프로그램을 만들어 봅시다.

[ 실행 결과 1 ]
*
**
***
****

[ 실행 결과 2 ]
*
**
***
****
*
**
***
****

[ 실행 결과 3 ]
     *
    ***
   *****
  *******
 *********
***********

for i in range(1, 5):
    print("*" * i)

# i = 1
# while i <= 4:
#     print("*" * i)
#     i = i + 1

for i in range(1, 3):
    for k in range(1, 5):
        print("*" * k)

# i, k = 1, 1
# while i <= 2:
#     while k <= 4:
#         print("*" * k)
#         k = k + 1
#     i = i + 1
#     k = 1

i, k = 5, 1
while i >= 0:
    print("{0}{1}".format(" " * i, "*" * (2 * k - 1)))
    i = i - 1
    k = k + 1
</pre>

<pre>
우리가 만드는 간단 계산기는 사용자로부터 두 개의 숫자와 한 개의 연산자를 입력 받아
그 연산자에 따른 계산을 수행하고, 덧셈(+), 뺄셈(-), 곱셈(*), 나눗셈(/)을 지원합니다.
여기에 사용자가 아무 것도 입력하지 않고 엔터만 쳐도 에러가 발생하지 않도록
사용자 입력에 대해 기본값을 적용할 것입니다.
또한 프로그램의 진행 여부에 대해서 사용자가 “n” 또는 “N”를 입력하면 프로그램을
종료하도록 하고, 그 외의 입력에 대해선 계속 진행을 의미하는 기능을 추가하여
프로그램을 만들어 봅시다.

[ 실행 결과 1 ]
첫 번째 숫자를 입력하세요: 2
연산자를 입력하세요 (+, -, *, /): +
두 번째 숫자를 입력하세요: 3
2 + 3 = 5
계속 진행하시겠습니까? (종료: n|N) n
프로그램을 종료합니다...

[ 실행 결과 2 ]
첫 번째 숫자를 입력하세요:
연산자를 입력하세요 (+, -, *, /):
두 번째 숫자를 입력하세요:
0 + 0 = 0
계속 진행하시겠습니까? (종료: n|N) y
첫 번째 숫자를 입력하세요: 2
연산자를 입력하세요 (+, -, *, /): /
두 번째 숫자를 입력하세요:
2 / 1 = 2.0
계속 진행하시겠습니까? (종료: n|N)
첫 번째 숫자를 입력하세요: 2
연산자를 입력하세요 (+, -, *, /): *
두 번째 숫자를 입력하세요:
2 * 0 = 0
계속 진행하시겠습니까? (종료: n|N)
첫 번째 숫자를 입력하세요: 2
연산자를 입력하세요 (+, -, *, /): $
두 번째 숫자를 입력하세요:
'$' 는 본 프로그램에서는 지원하지 않는 연산자입니다.
계속 진행하시겠습니까? (종료: n|N) n
프로그램을 종료합니다...

while True:

    going = "n"

    operand1 = input("첫 번째 숫자를 입력하세요: ")
    operator = input("연산자를 입력하세요 (+, -, *, /): ")
    operand2 = input("두 번째 숫자를 입력하세요: ")

    if operand1 == "":
        operand1 = 0

    if operator == "":
        operator = "+"

    if operand2 == "" and operator == "/":
        operand2 = 1
    elif operand2 == "" and operator != "/":
        operand2 = 0

    operand1 = int(operand1)
    operand2 = int(operand2)

    if operator == "+":
        print("{0} + {1} = {2}".format(operand1, operand2, operand1 + operand2))
    elif operator == "-":
        print("{0} - {1} = {2}".format(operand1, operand2, operand1 - operand2))
    elif operator == "*":
        print("{0} * {1} = {2}".format(operand1, operand2, operand1 * operand2))
    elif operator == "/":
        print("{0} / {1} = {2:.2f}".format(operand1, operand2, operand1 / operand2))
    else:
        print("'{0}' 는 본 프로그램에서는 지원하지 않는 연산자입니다.".format(operator))

    going = input("계속 진행하시겠습니까? (종료: n|N) ")
    if going == "n" or going == "N":
        break

print("프로그램을 종료합니다...")
</pre>

<pre>
A 쇼핑몰에서는 회원 등급에 따라 할인 서비스를 제공합니다.
회원 등급에 따른 할인율은 다음과 같습니다.
(S = 실버, G = 골드, V = VIP)
| 등급     | 할인율 |
|----------|--------|
| "S" | 5%     |
| "G"   | 10%    |
| "V"    | 15%    |
상품의 가격 price와 구매자의 회원 등급을 나타내는 문자열 grade가 매개변수로 주어질 때,
할인 서비스를 적용한 가격을 return 하도록 solution 함수를 완성해주세요.
---
#####매개변수 설명
상품의 가격 price와 회원 등급 grade가 매개변수로 주어집니다.
* grade는 "S", "G", "V" 세 가지 중 하나입니다.
---
#####return 값 설명
할인한 가격을 return 하도록 solution 함수를 작성해주세요.
---
#####예시
| price | grade    | return |
|-------|----------|--------|
| 2500  | "V"    | 2125   |
| 96900 | "S" | 92055  |
##### 예시 설명
예시 #1
2500원의 15%는 375원 입니다. 2500 - 375 = 2125 입니다.
예시 #2
96900원의 5%는 4845원 입니다. 96900 - 4845 = 92055 입니다.

def solution(price, grade):
    answer = 0
    
    return answer


price1 = 2500
grade1 = "V"
ret1 = solution(price1, grade1)

print("Solution: return value of the function is", ret1, ".")
    
price2 = 96900
grade2 = "S"
ret2 = solution(price2, grade2)

print("Solution: return value of the function is", ret2, ".")
</pre>
