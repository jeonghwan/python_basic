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

<pre>
시작 날짜와 끝 날짜가 주어질 때, 두 날짜가 며칠만큼 떨어져 있는지(D-day)를 구하려 합니다.
시작 날짜의 월, 일을 나타내는 start_month, start_day, 끝 날짜의 월, 일을 나타내는 end_month, end_day가
매개변수로 주어질 때, 시작 날짜와 끝 날짜가 며칠만큼 떨어져 있는지 return 하도록 solution 함수를 작성했습니다.
이때, 주어진 날짜가 1월 1일로부터 얼만큼 지났는지를 반환하는 func_a 함수를 작성했습니다.
전체 코드가 올바르게 동작할 수 있도록 빈칸을 알맞게 채워주세요.

---
##### 매개변수 설명
시작 날짜의 월, 일을 나타내는 start_month, start_day, 끝 날짜의 월, 일을 나타내는 end_month, end_day가
solution 함수의 매개변수로 주어집니다.
* 잘못된 날짜가 주어지는 경우는 없습니다.
* 끝 날짜는 항상 시작 날짜보다 뒤에 있는 날이 주어집니다.
* 끝 날짜가 다음 해로 넘어가는 경우는 주어지지 않습니다.
  * 즉, start_month <= end_month를 항상 만족합니다.
  * start_month = end_month라면 start_day <= end_day를 항상 만족합니다.
* 각 달의 날짜 수는 1월부터 순서대로 [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31] 이며, 윤년은 고려하지 않습니다.

---
##### return 값 설명
시작 날짜와 끝 날짜가 며칠만큼 떨어져 있는지 return 해주세요.

---
##### 예시
| start_month | start_day | end_month | end_day | return |
|-------------|-----------|-----------|---------|--------|
| 1           | 2         | 2         | 2       | 31     |
##### 예시 설명
시작 날짜는 1월 2일이고, 끝 날짜는 2월 2일입니다.
* 1월 2일은 1월 1일로부터 1일만큼 지난 날입니다.
* 2월 2일은 1월 1일로부터 32일만큼 지난 날입니다.
* 32 - 1 = 31입니다.
* 따라서 1월 2일과 2월 2일은 31일만큼 떨어져 있습니다.

def func_a(month, day):
    month_list = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    total = 0;
    for i in @@@:
        total += @@@
    total += @@@
    return total - 1

def solution(start_month, start_day, end_month, end_day):
    start_total = func_a(start_month, start_day)
    end_total = func_a(end_month, end_day)
    return end_total - start_total

start_month = 1
start_day = 2
end_month = 2
end_day = 2
ret = solution(start_month, start_day, end_month, end_day)

print("Solution: return value of the function is", ret, ".")
</pre>

<pre>
A 학교에서는 단체 티셔츠를 주문하기 위해 학생별로 원하는 티셔츠 사이즈를 조사했습니다.
선택할 수 있는 티셔츠 사이즈는 작은 순서대로 "XS", "S", "M", "L", "XL", "XXL" 총 6종류가 있습니다.
학생별로 원하는 티셔츠 사이즈를 조사한 결과가 들어있는 리스트 shirt_size가 매개변수로 주어질 때,
사이즈별로 티셔츠가 몇 벌씩 필요한지 가장 작은 사이즈부터 순서대로 리스트에 담아 return 하도록
함수를 완성해주세요.
---
##### 매개변수 설명
학생별로 원하는 사이즈를 조사한 결과가 들어있는 리스트 shirt_size가 함수의 매개변수로 주어집니다.
* shirt_size 에는 치수를 나타내는 문자열 "XS", "S", "M", "L", "XL", "XXL" 이 들어있습니다.
---
##### return 값 설명
티셔츠가 사이즈별로 몇 벌씩 필요한지 가장 작은 사이즈부터 순서대로 리스트에 담아 return 해주세요.
* return 하는 리스트에는 [ "XS" 개수, "S" 개수, "M" 개수, "L" 개수, "XL" 개수, "XXL" 개수] 순서로
들어있어야 합니다.
---
##### 예시
| shirt_size                       | return        |
|----------------------------------|---------------|
| ["XS", "S", "L", "L", "XL", "S"] | [1, 2, 0, 2, 1, 0] |
##### 예시 설명
* "XS"와 "XL"은 각각 한 명씩 신청했습니다.
* "S"와 "L"은 각각 두 명씩 신청했습니다.
* "M"과 "XXL"을 신청한 학생은 없습니다.
따라서 순서대로 [1, 2, 0, 2, 1, 0]을 리스트에 담아 return 하면 됩니다.


def solution(shirt_size):
    result = []
    for i in range(6):
        result.append(0)

    for v in shirt_size:
        if v == "XS":
            result[0] += 1
        elif v == "S":
            result[1] += 1
        elif v == "M":
            result[2] += 1
        elif v == "L":
            result[3] += 1
        elif v == "XL":
            result[4] += 1
        elif v == "XXL":
            result[5] += 1
    return result


shirt_size = ["XS", "S", "L", "L", "XL", "S"]
ret = solution(shirt_size)

print("Solution: return value of the function is ", ret, " .")
</pre>

<pre>
A 대학에서는 수준별 영어 강의를 제공하고 있습니다. 초급 영어 강의는 토익시험에서 650점 이상 800점 미만의 성적을 취득한
학생만을 수강대상으로 하고 있습니다. 초급 영어 강의에 수강신청한 사람이 10명일 때, 이 중에서 몇명이 수강 대상에 해당하는지
확인하려합니다.
수강신청자들의 토익 성적이 들어있는 리스트 scores가 매개변수로 주어질 때, 수강 대상자들의 인원수를 return 하도록
solution 함수를 작성했습니다. 그러나, 코드 일부분이 잘못되어있기 때문에, 몇몇 입력에 대해서는 올바르게 동작하지 않습니다.
주어진 코드에서 한 줄만 변경해서 모든 입력에 대해 올바르게 동작하도록 수정해주세요.
---
#####매개변수 설명
수강신청자들의 토익 성적이 들어있는 리스트 scores가 solution 함수의 매개변수로 주어집니다.
* scores의 원소는 500 이상 990 이하의 정수입니다.
* scores의 길이는 10입니다.
---
#####return 값 설명
수강 대상자들의 인원수를 return 해주세요.
---
#####예시
| scores                                             | return |
|----------------------------------------------------|--------|
| [650, 722, 914, 558, 714, 803, 650, 679, 669, 800] | 6      |
#####예시 설명
|점수| 650 | 722 | 914 | 558 | 714 | 803 | 650 | 679 | 669 | 800 |
|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|
|수강 대상| O   | O   | X   | X   | O   | X   | O   | O   | O   | X   |
650점 이상 800점 미만의 성적을 취득한 학생이 수강대상이므로, 800점을 취득한 학생은 수강대상이 아닙니다.
따라서, 6명이 수강 대상입니다.

def solution(scores):
    count = 0
    for s in scores:
        if 650 <= s or s < 800:
            count += 1
    return count

scores = [650, 722, 914, 558, 714, 803, 650, 679, 669, 800]
ret = solution(scores)

print("Solution: return value of the function is", ret, ".")
</pre>

<pre>
앞에서부터 읽을 때와 뒤에서부터 읽을 때 똑같은 단어 또는 문장을 팰린드롬(palindrome)이라고 합니다.
예를 들어서 racecar, noon은 팰린드롬 단어입니다. 
소문자 알파벳, 공백(" "), 그리고 마침표(".")로 이루어진 문장이 팰린드롬 문장인지 점검하려 합니다.
문장 내에서 알파벳만 추출하였을 때에 팰린드롬 단어이면 팰린드롬 문장입니다.
예를 들어, "Never odd or even."과 같은 문장은 팰린드롬입니다.
소문자 알파벳, 공백(" "), 그리고 마침표(".")로 이루어진 문장 sentence가 주어질 때 팰린드롬인지 아닌지를
return 하도록 solution 함수를 작성했습니다. 그러나, 코드 일부분이 잘못되어있기 때문에, 몇몇 입력에 대해서는
올바르게 동작하지 않습니다. 주어진 코드에서 한 줄만 변경해서 모든 입력에 대해 올바르게 동작하도록 수정해주세요.
---
##### 매개변수 설명
소문자 알파벳, 공백(" "), 그리고 마침표(".")로 이루어진 문장 sentence가 solution 함수의 매개변수로 주어집니다.
* sentence에는 적어도 하나의 알파벳이 포함되어 있습니다.
* setntence의 각 문자는 소문자 알파벳, 공백(" "), 또는 마침표(".")입니다.
---
##### return 값 설명
주어진 문장이 팰린드롬인지 아닌지를 return 해주세요.
---
##### 예시
| sentence             	| return 	|
|----------------------	|--------	|
| "never odd or even." 	| true   	|
| "palindrome"         	| false  	|
##### 예시 설명
예시 #1
알파벳과 숫자만 추출하여 소문자로 변환해보면 "neveroddoreven"이 되며 이 단어는 팰린드롬입니다.
예시 #2
문장의 맨 앞 문자인 "p"와 맨 뒤 문자인 "e"가 다르므로 팰린드롬이 아닙니다.

def solution(sentence):
    str = ''
    for c in sentence:
        if c != '.' or c != ' ':
            str += c
    size = len(str)
    for i in range(size // 2):
        if str[i] != str[size - 1 - i]:
            return False
    return True


sentence1 = "never odd or even."
ret1 = solution(sentence1)

print("Solution: return value of the function is", ret1, ".")
    
sentence2 = "palindrome"
ret2 = solution(sentence2)

print("Solution: return value of the function is", ret2, ".")
</pre>

<br>

<pre>
#문제1 (40점)
여행객들의 총 교통비를 계산하려고 합니다. 교통편은 "Bus", "Ship", "Airplane" 총 3가지입니다. 
나이가 20살 이상이면 어른 요금을, 그렇지 않으면 어린이 요금을 받습니다. 
각 교통편별 가격은 다음과 같습니다.
|   | 어른 | 어린이 |
|---|---|---|
| Bus | 40,000원  | 15,000원 |
| Ship |  30,000원 | 13,000원 |
| Airplane | 70,000원 | 45,000원 |
여행객들이 10명 이상인 경우 연령에 따라 할인을 받습니다.
| 어른 | 어린이 |
|---|---|
| 10% | 20% |
여행객들의 나이를 담고 있는 리스트 member_age와 교통편인 transportation이 매개변수로 주어질 때, 
총 교통비를 return 하도록 solution 함수를 완성해주세요.
---
#####매개변수 설명
여행객들의 나이를 담고 있는 리스트 member_age와 교통편인  transportation이 solution 함수의 
매개변수로 주어집니다.
* transportation은 "Bus" 또는 "Ship" 또는 "Airplane" 입니다.
---
#####return값 설명
교통비 총액을 return 해주세요.
---
#####예시
| member_age | transportation | return |
|---|---|---|
| [13, 33, 45, 11, 20] | "Bus" | 150000 |
| [25, 11, 27, 56, 7, 19, 52, 31, 77, 8] | "Ship" | 203600 |
---
#####예시 설명
예시 #1
여행객들의 나이는 [13, 33, 45, 11, 20]이고 교통수단으로는 "Bus"를 이용하려합니다. 
나이가 20살 미만인 인원은 2명으로 어린이 요금은 30,000원이고 나이가 20살 이상인 인원은 3명으로 
어른 요금은 120,000원입니다. 따라서 교통비 총액은 150,000원입니다.

예시 #2
여행객들의 나이는 [25, 11, 27, 56, 7, 19, 52, 31, 77, 8]이고 교통수단으로는 "Ship"을 이용하려합니다. 
여행객들이 10명 이상이므로 교통비가 할인됩니다. 나이가 20살 미만인 인원은 4명으로 어린이 요금은 
41,600원이고 나이가 20살 이상인 인원은 6명으로 어른 요금은 162,000원입니다. 
따라서 교통비 총액은 203,600원입니다.

def solution(member_age, transportation):
	pass


member_age1 = [13, 33, 45, 11, 20]
transportation1 = "Bus"
ret1 = solution(member_age1, transportation1)

print("solution 함수의 반환 값은", ret1, "입니다.")

member_age2 = [25, 11, 27, 56, 7, 19, 52, 31, 77, 8]
transportation2 = "Ship"
ret2 = solution(member_age2, transportation2)

print("solution 함수의 반환 값은", ret2, "입니다.")
</pre>


<pre>
#문제 (30점)
학생들의 시험 점수가 주어졌을 때, n번 학생이 몇 등인지 구하려 합니다. 학번은 0번부터 시작하며, 시험 점수는 학번순으로 주어집니다.
학생들의 시험 점수가 번호순으로 들어있는 리스트 scores와 학번 n이 solution 함수의 매개변수로 주어질 때, 
n번 학생의 등수를 return 하도록 solution 함수를 작성하려 합니다. 
코드가 올바르게 동작하도록 빈칸에 주어진 func_a, func_b, func_c 함수와 매개변수를 알맞게 채워주세요.
---
#####매개변수 설명
학생들의 시험 점수가 번호순으로 들은 리스트 scores와 학번 n이 solution 함수의 매개변수로 주어집니다.
* 점수는 0점 이상 100점 이하이며 동점자는 없습니다.
* n은 0 이상 (scores의 길이 - 1) 이하의 정수입니다.
---
#####return 값 설명
n번 학생의 등수를 return 해주세요.
---
#####예시
| scores           | n | result |
|------------------|---|--------|
| [20, 60, 98, 59] | 3 | 3      |
#####예시 설명
* 3번 학생의 점수는 59점입니다.
* 점수를 내림차순으로 정렬하면 [98, 60, 59, 20]입니다.
* 정렬된 점수에서 59는 3번째에 있습니다.
따라서 3번 학생은 3등입니다.

def func_a(scores, score):
    rank = 1
    for s in scores:
        if s == score:
            return rank
        rank += 1
    return 0

def func_b(arr):
    arr.sort(reverse=True)

def func_c(arr, n):
    return arr[n]

def solution(scores, n):
    score = func_@@@(@@@)
    func_@@@(@@@)
    answer = func_@@@(@@@)
    return answer


scores = [20, 60, 98, 59]
n = 3
ret = solution(scores, n)

print("solution 함수의 반환 값은", ret, "입니다.")
</pre>


<pre>
#문제3 (30점)
A씨가 하루에 TV를 두 대 이상 트는 시간을 알아내려합니다. A씨는 매일 세 프로그램을 시청합니다. 
프로그램 방송 시간이 겹칠 때는 TV를 여러 대 켜서 모든 프로그램을 봅니다.
예를 들어 두 프로그램 방송 시간대가 겹치면 TV를 두 대 켜고, 세 프로그램 방송 시간이 겹치면 TV를 세 대 켭니다.
세 프로그램 방영 시작 시각과 끝 시각이 담긴 2차원 리스트 programs가 매개변수로 주어질 때, 
하루에 TV를 2대 이상 트는 총 시간을 return 하도록 solution 함수를 작성했습니다. 
그러나, 코드 일부분이 잘못되어있기 때문에, 몇몇 입력에 대해서는 올바르게 동작하지 않습니다. 
주어진 코드에서 한 줄만 변경해서 모든 입력에 대해 올바르게 동작하도록 수정하세요.
---
#####매개변수 설명
3개의 프로그램이 시작되는 시각과 끝나는 시각이 담긴 2차원 리스트 programs가 solution 함수의 매개변수로 주어집니다.
* programs 리스트의 각 원소는 각 프로그램의 방송 시간이 [시작 시각, 끝 시각] 형태로 들어있습니다.
* 프로그램의 시작 시각과 끝 시각은 0 이상 24 이하의 정수입니다.
* 프로그램의 시작 시각은 끝 시각보다 항상 빠릅니다.
---
#####return 값 설명
A 씨가 TV를 2대 이상 트는 총 시간을 return 해주세요.
---
#####예시
| programs            		 | return |
|--------------------------|--------|
| [[1, 6], [3, 5], [2, 8]] | 4     |
---
#####예시 설명
2대의 TV를 트는 시간이 2시부터 3시까지, 5시부터 6시까지 총 2시간이고
3대의 TV를 트는 시간이 3시부터 5시까지 총 2시간입니다.
따라서 TV를 2대 이상 트는 시간은 총 4시간입니다.


def solution(programs):
    answer = 0
    used_tv = [0] * 25

    for program in programs:
        for i in range(program[0], program[1]):
            used_tv[i] = used_tv[i] + 1
    
    for i in used_tv:
        if i >= 1:
            answer = answer + 1
    return answer


programs = [[1, 6], [3, 5], [2, 8]]
ret = solution(programs)

print("solution 함수의 반환 값은", ret, "입니다.")
</pre>
