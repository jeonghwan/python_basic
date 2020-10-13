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
우리가 만들어 볼 간단 계산기는 사용자로부터 두 개의 숫자와 한 개의 연산자를 입력 받아 그 연산자에 따른 계산을 수행할 것입니다. 
연산자는 +(덧셈), -(뺄셈), *(곱셈), /(나눗셈)을 지원하도록 합니다.

[결과1]
첫 번째 숫자를 입력하세요: 2 
연산자를 입력하세요 (+, -, *, /): + 
두 번째 숫자를 입력하세요: 3 
2 + 3 = 5

[결과2]
첫 번째 숫자를 입력하세요: 2 
연산자를 입력하세요 (+, -, *, /): # 
두 번째 숫자를 입력하세요: 3 
'#'는 본 프로그램에서 지원하지 않는 연산자입니다.
</pre>

<pre>
다음 세 가지 결과의 패턴을 각각 분석해 이번 장에서 배운 for문과 while문과 같은 반복문을 이용한 프로그램을 만들어 봅시다.

[결과1]
*
**
***
****

[결과2]
*
**
***
****
*
**
***
****

[결과3]
     *
    ***
   *****
  *******
 *********
***********
</pre>
