![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/c628fb94-5423-4836-a3c1-d0aaf253ac80)# shinchaewon.data-preprocessing
# 1장 파이썬의 기초
## 1.1 기초
*코멘트(주선)처리:R과 동일하게 #
```
# 파이썬 주석처리는 코드 앞에 #
import io
a = 1
print(a)
```
```
## 1
```
* help기능
```
import io
help("print")
```
```
## Help on built-in function print in module builtins:
## 
## print(...)
##     print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
##     
##     Prints the values to a stream, or to sys.stdout by default.
##     Optional keyword arguments:
##     file:  a file-like object (stream); defaults to the current sys.stdout.
##     sep:   string inserted between values, default a space.
##     end:   string appended after the last value, default a newline.
##     flush: whether to forcibly flush the stream.
```
* 화면출력(print()함수)
```
import io
print("print ...")
```
```
## print ...
```
* 변수 식별자의 명명법
  * 항상 알파벳이나 _ (밑줄)로 시작
  * 두번째 이후는 알파벳, _, 0~9으로 구성
  * 대/소문자 구분
```
#-*- coding: utf-8 -*-
a = 1
_b12 = '파이썬 쌩초보입니다..'
print(a, _b12, "\n")
```
```
## 1 파이썬 쌩초보입니다..
```
* 들여쓰기
  * 같은 레벨의 코드는 같은 열부터 작성
  * 하위레벨의 코드는 공백 4개 들여쓰기
```
a = 1
print(a)
```
```
## 1
```
```
if a == 1:
    print(a) # 공백 4개 이후 코드 작성
```
```
## 1
```
## 1.2 기본 자료형

* 파이썬의 기본 자료형은
  1. 리터럴 상수
  2. 리스트(list)
  3. 튜플 (tuple)
  4. 딕션너리 (dictionary)
  5. 집합 (set) 등으로 구성되어 있음
### 1.2.1 리터럴 상수
1. 숫자형: 정수형(integer)/부동소수점형(Float)
   * 정수형: ex>2,3,4,5
   * 소수점 숫자: ex>3.23, 52.3E-4
2. 문자열
   * 작은따옴표(' '), 큰따옴표(" "), 따옴표 세 개 (''' ... ''')
   * 문자열 안에서 작은/큰 따옴표 사용 가능
```
x = 'this is ...'
x = "this is a ..."
x = '''This is a multi-line string. 
This is the 1st line.
This is the 2nd line.
'''
print(x)
```
```
## This is a multi-line string. 
## This is the 1st line.
## This is the 2nd line.
```
* 문자열의 인덱싱/슬라이싱: 문자열의 부분을 접근하는 방법
```
z = '나는 홍익대학교 서울캠퍼스 산업-데이터공학과에 다니고 있습니다.'
```
■  아래의 대괄호 안에 :2는 문자열의 첫(0번째) 문자 부터 2번째 문자 직전까지를 나타냄, 즉, 0~1번째 문자 (‘나는’)
```
z[:2]
```
```
## '나는'
```
■ 위의 문자열에서 홍익대학교를 추출하려면?
```
z[3:8]
```
```
## '홍익대학교'
```
### 1.2.2 리스트(list)
   1. 리스트의 생성 방법
```
리스트명 = [요소1, 요소2, ..., 요소n]
```
   ＊ 리스트 생성
```
a = [] # 또는 a= list()
b = [1, 2, 3]
c = ['Life', 'is', 'too', 'short']
d = [1, 2, 'Life', 'is']
e = [1, 2, ['Life', 'is']]
e
```
```
## [1, 2, ['Life', 'is']]
```
2. 리스트의 특징
   * 순서화된 요소(인덱스 이용)
   * 추가/변경/삭제 가능
3. 리스트 함수
   1. 요소의 개수(len)
```
len(e)
```
```
## 3
```
2. 요소 삽입 (insert): 전해진 위치에 삽입
```
a = [1, 4, 3, 2]
a.insert(1, 7)  #두번째(1)위치에 7을 삽입
a
```
```
## [1, 7, 4, 3, 2]
```
3. 추가(append): 맨뒤에 추가
```
a = [1, 4, 3, 2]
a.append(4)     # 리스트의 맨 뒤에 `4`를 추가
a
```
```
## [1, 4, 3, 2, 4]
```
4. 리스트 정렬(sort): 역순 정렬은 reverse=True 추가
```
a = [1, 4, 3, 2]
b = sorted(a, reverse=True)
print(b)
```
```
## [4, 3, 2, 1]
```
```
a.sort(reverse=True)
print(a)
```
```
## [4, 3, 2, 1]
```
5. 위치 반환(index): 주어진 값(요소)이 나타나는 리스트의 첫번째 위치
```
print(a)
```
```
## [4, 3, 2, 1]
```
```
a.index(4) # 4는 3번째 (0부터 시작하므로 2가 반환됨)
```
```
## 0
```
6. 요소 추출 후 삭제(pop): 정해진 요소값(3)을 추출하고 리스트에서는 삭제됨
```
print(a)
```
```
## [4, 3, 2, 1]
```
```
print(a.pop(3))
```
```
## 1
```
```
a
```
```
## [4, 3, 2]
```
7. 인덱싱과 슬라이싱
```
a = ['파이썬', '프로그램은', '빅데이터분석을', '위한' , '필수적인', '도구이다.']
print(a[0]) # 0번째 요소 추출
```
```
## 파이썬
```
```
print(a[-1]) # 마지막 첫번째 값
```
```
## 도구이다.
```
```
print(a[-2:]) # 뒤로 두번째부터 마지막까지
```
```
## ['필수적인', '도구이다.']
```
```
print(a[:2]) # 0부터 2직전 까지 요소값 
```
```
## ['파이썬', '프로그램은']
```
```
print(a[1:]) # 1부터 마지막까지
```
```
## ['프로그램은', '빅데이터분석을', '위한', '필수적인', '도구이다.']
```
```
print(a[1:3]) # 1부터 3직전(즉, 2)까지
```
```
## ['프로그램은', '빅데이터분석을']
```
### 1.2.3 튜플 (tuple)
1. 튜플(tuple)과 리스타(list)의 차이점
   1. 리스트는 [ ], 튜플은 ( )
   2. 리스트는 요소값의 삭제, 수정이 가능, 튜플은 불가
2. 튜플의 생성
```
zoo = ('python', 'elephant', 'penguin')
print(zoo)
```
```
## ('python', 'elephant', 'penguin')
```
3. 튜플 관련 함수
```
len(zoo) # 튜플의 길이    
```
```
## 3
```
```
new_zoo = 'monkey', 'camel', zoo # 추가
new_zoo[2] #인덱싱/슬라이싱
```
```
## ('python', 'elephant', 'penguin')
```
### 1.2.4  딕셔너리 (dictionary)
1. 특징
   * key 와 value 의 쌍을 갖는 자료형
     ■ {key_1: value_1, ..., key_n: value_n,}
   * key는 반드시 유일해야함 (중복되면 마지막 키에 해당되는 것만 저장됨)
   * key에는 리스트 사용불가, 즉 상수만 사용 가능
2. 예제
```
email = {'김진욱': 'jukim@dongguk.ac.kr',
       '김동국': 'dg@dongguk.ac.kr',
       '신채원': 'sshwan@dongguk.edu',
       '홍길동': 'gildong@gmail.com'
    }
email
```
```
## {'김진욱': 'jukim@dongguk.ac.kr', '김동국': 'dg@dongguk.ac.kr', '신채원': 'sshwan@dongguk.edu', '홍길동': 'gildong@gmail.com'}
```
＊keys(), items()
```
print(email['김진욱'])
```
```
## jukim@dongguk.ac.kr
```
```
print(email.items())
```
```
## dict_items([('김진욱', 'jukim@dongguk.ac.kr'), ('김동국', 'dg@dongguk.ac.kr'), ('신채원', 'sshwan@dongguk.edu'), ('홍길동', 'gildong@gmail.com')])
```
```
print(email.keys())
```
```
## dict_keys(['김진욱', '김동국', '신채원', '홍길동'])
```
* for 문에서
```
for name, address in email.items():
    print ('{}의 이메일은 {}입니다.'.format(name, address))
```
```
## 김진욱의 이메일은 jukim@dongguk.ac.kr입니다.
## 김동국의 이메일은 dg@dongguk.ac.kr입니다.
## 신채원의 이메일은 sshwan@dongguk.edu입니다.
## 홍길동의 이메일은 gildong@gmail.com입니다.
```
### 1.2.5 집합 (set)
* 정렬되지 않은 단순 객체의 묶음
* 객체의 순서나 중복의 상관 
```
bri = set(['brazil', 'russia', 'india'])
'india' in bri       # 원소의 포함 여부  
```
```
## True
```
```
'usa' in bri
```
```
## False
```
```
bric = bri.copy()    # 다른 객체로 복사
bric.add('china')    # 원소 추가
bric.issuperset(bri) # 집합간 포함관계
```
```
## True
```
```
bri.remove('russia') # 원소 삭제
bri & bric           # 교집합
```
```
## {'brazil', 'india'}
```
## 1.3 연산자 (operator)
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/3e8a6181-16bf-466c-828c-1fa2c20d4289)

1. [사칙연산] +, -, *, /
```
x = 3 + 5  # 더하기
y = 3 - 5  # 빼기
x, y
```
```
## (8, -2)
```
```
y= 2 * 3 # 곱하기 연산
y
```
```
## 6
```
```
x = '통계' * 3 # 문자열인 경우
x
```
```
## '통계통계통계'
```
```
x = 13 / 3
x
```
```
## 4.333333333333333
```
2. [거듭제곱 연산] **
```
# 파이썬
x = 3 ** 4
x
```
```
## 81
```
```
# R
x = 3^4
x
```
```
## [1] 81
```
3. [나머지 연산] %
```
# 파이썬
x = 13 % 3
x
```
```
## 1
```
```
# R
x = 13 %% 3
x
```
```
## [1] 1
```
4. [비트연산] &, |, ^ (and, or, xor)
```
x = 5 & 3    
#  5  = 0000 0101 <= 이진수
#  3  = 0000 0011 <= 이진수
# 5&3 = 0000 0001 <= 이진수
#               1 <= 십진수
x
```
```
## 1
```
```
x = 5|3
y = 5 or 3
#  5  = 0000 0101 <= 이진수
#  3  = 0000 0011 <= 이진수
# 5|3 = 0000 0111 <= 이진수
#               7 <= 십진수
x, y
```
```
## (7, 5)
```
```
#  5  = 0000 0101 <= 이진수
#  3  = 0000 0011 <= 이진수
# 5^3 = 0000 0110 <= 이진수
#               6 <= 십진수
5^3
```
```
## 6
```
```
x= ~5  # 5의 1에 대한 보수 => -(x + 1) => -6
#  5   =  0000 0101 <= 이진수
#flip  =  1111 1010
#shift =1 1111 010 0
# +1   =1 1111 0101
#flip  =1 0000 1010  
# -------------------------    
#       - 0000 1010 ==> -6
x
```
```
## -6
```
5. [논리연산] <, >, <=, >=, ==, !=, not, and, or
```
5 < 3
```
```
## False
```
```
2 != 3
```
```
## True
```
```
x= True;
not x
```
```
## False
```
```
True and False
```
```
## False
```
```
True or False
```
```
## True
```
```
a = [1,2,3] # 
b = [1,2,3]
c = a       # c has same reference of a
print('a is b:', a is b) # 객체의 주소(references)를 비교
```
```
## a is b: False
```
```
print('a == b:', a == b) # 객체의 값을 비교
```
```
## a == b: True
```
```
print('a is c:', a is c)
```
```
## a is c: True
```
```
print('a == c', a == c)
```
```
## a == c True
```
## 1.4 제어문
   * 파이썬 제어문에는 조건문과 순환문이 있다
### 1.4.1 조건문
   * if, elif, else 구문의 기본형식
```
   if 조건1:
      수행문1
   elif 조건2:
      수행문2
   else:
      수행문3
```
* 삼항연산자를 이용하는 방법
```
  x = [조건이 참일 때 결과]  if 조건 else [거짓일때 결과]
```
* 예제 1
```
# python
x = 120
if x > 100:
    o = 'good'
else:
    o = 'common'
print(o)
```
```
## good
```
```
# R
x = 120
if (x > 100){
    o = 'good'
}else{
    o = 'common'
}
print(o)
```
```
## [1] "good"
```
* 예제 2
```
# python
o = 'good' if x > 100 else 'common'
print(o)
```
```
## good
```
```
# R 은 ifelse 함수 이용
o = ifelse(x > 100, 'good', 'common')
print(o)
```
```
## [1] "good"
```
## 1.4.2. 반복문/순환문/loop
1. while 문
   * while 조건은 조건이 참인 경우 반복 실행
   * 기본형식
```
while 조건:
   수행문1
   수행문2
   ...
```
   * 예제 1
```
# python
i = 0
total = 0
while i < 10:
    total += i
    i += 1
print(total)
```
```
## 45
```
```
# R
i = 0
total = 0
while(i < 10){
    total = total + i
    i = i + 1
}
print(total)
```
```
## [1] 45
```
   * 예제 2
```
# python
i = 1
total = 0
while True:
    total += i
    i += 1
    if i > 10:
      break
print(total)
```
```
## 55
```
```
# R
i = 1
total = 0
while(TRUE){
    total = total + i
    i = i + 1
    if(i > 10) break
}
print(total)
```
```
## [1] 55
```
2. for문
   * 기본형
```
for 조건:
   수행문....


for 조건:
   수행문1
else:
   수행문2
```
   * Example
```
for i in range(1, 5):
    print (i)
else:
    print ('The for loop is over')
```
```
## 1
## 2
## 3
## 4
## The for loop is over
```
* Same Example with R
```
for(i in 1:5){
    print (i)
}
```
```
## [1] 1
## [1] 2
## [1] 3
## [1] 4
## [1] 5
```
```
# R에는 for ... else 구문이 없음
print('The for loop is over')
```
```
## [1] "The for loop is over"
```
3. break: 루프 문을 강제로 빠져나오거나 정지시킬 때 사용
```
s = 0
while True:
  if s > 10:
    print (s, 's > 10 so finish...')
    break
  else: 
    print ('s = ',s)
    s += 1
```
```
## s =  0
## s =  1
## s =  2
## s =  3
## s =  4
## s =  5
## s =  6
## s =  7
## s =  8
## s =  9
## s =  10
## 11 s > 10 so finish...
```
4. contunue: 실행중인 루프 블록의 나머지를 실행하지 않고, 다음 루프로 넘김
```
# python
total = 0
for s in [1,2,3,4,5,6,7,8]:
  if s % 2 == 1:
      continue
  total += s
print (total)
```
```
## 20
```
```
# R
total = 0
for(s in c(1,2,3,4,5,6,7,8)){
  if(s %% 2 == 1) 
    next   # <===== 
  total = total + s
}
print(total)
```
```
## [1] 20
```
## 1.5 예외처리
* 함수는 입력값이 정해진 규칙에 맞게 입력된 경우만 정상 작동
* 잘못된 입력값을 입력하면 오류 발생
* 이러한 경우, 입력이 잘못되었더라도 그에 맞는 결과를 출력하도록 코드를 작성하는 것이 필요
* R에서 예외처리는 try() 또는 tryCatch() 함수를 이용한다.
* 정상적인 입력시
```
float('1.414159')
```
```
## 1.414159
```
* 비정상 입력: 오류발생
```
a = 'abcd'
float(a)
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/e18516d1-7078-44f6-9aa1-ff14614c7386)
* 오류 발생
* 예 1: try ... except
```
a = 'abcd'
try:
    float(a)
except:
    print(a)
```
```
## abcd
```
* 예2: try ... except ... finally
```
f = open(path, 'w')
try:                 # try
  write_to_file(f)
except:              # 예외처리
  print('Failed')
else:
  print('Succeeded') # 정상처리
finally:             # 정상 및 예외처리
  f.close()
```
## 1.6 파이썬 함수
### 1.6.1
1. 문법
```
def 함수이름(매개변수,...):
    함수 정의
    return() #반환값
# 함수호출    
함수이름(매개변수값들)
```
2. 예제 1: 매개변수 a, b값을 받아 값을 비교하여 출력하는 함수 print_max를 정의
```
# python 함수정의
def print_max(a,b):
    if a>b:
        print (a,'is maximum')
    elif a==b:
        print (a,'is equal to',b)
    else:
        print (b,'is maximum')
# 호출            
x=5; y=7
print_max(x,y)
```
```
## 7 is maximum
```
```
# R 함수정의
print_max = function(a,b){
    if(a>b){
        cat(a,'is maximum\n')
    }else if (a==b){
        cat(a,'is equal to',b, '\n')
    }else{
        cat(b,'is maximum\n')
    }
}
# 호출            
x=5; y=7
print_max(x,y)
```
```
## 7 is maximum
```
3. 예제 2
```
def add(a, b=0):
  """
  a와 b를 더하는 함수
  - a: 실수
  - a: 실수(디폴트=0)
  - return(a+b)
  """
  c = a+b
  return(c)

add(3,7)
```
```
## 10
```
```
add(25)
```
```
## 25
```
```
help(add)
```
```
## Help on function add in module __main__:
## 
## add(a, b=0)
##     a와 b를 더하는 함수
##     - a: 실수
##     - a: 실수(디폴트=0)
##     - return(a+b)
```
### 1.6.2
* 지역변수: 함수안에서만 사용되는 변수, 함수밖의 같은 이름의 변수와 관계없음
```
x=50 # 전역변수
def func(x):
    # 여기서 x는 지역변수
    print('x is',x)
    x=2
    print('Changed local x to',x)

func(x)
```
```
## x is 50
## Changed local x to 2
```
```
print('x is still',x)
```
```
## x is still 50
```
* 전역변수: 함수나 클래스 밖에서 선언된 변수가 함수안에 영향을 미치고, 함수안에서 변경가능
```
x=50
def func():
    global x # 전역변수
    print( 'x is',x)
    x=2
    print('Changed global x to',x)

func()
```
```
## x is 50
## Changed global x to 2
```
```
print('Value of x is',x)
```
```
## Value of x is 2
```
# 2장 Numpy
## 2.1 NumPy(넘파이) 특징
* 과학 계산을 위한 라이브러리
* 행렬/배열 처리 및 연산
* 난수생성
## 2.2 배열의 생성

1. 리스트에서 행렬/배열 생성

```
import numpy as np
a = [[1, 2, 3], [4, 5, 6]]
b = np.array(a)
print(b)

```
```
결과:
[[1 2 3]
 [4 5 6]]

```
``` 
print(b.ndim)  # 배열의 열수(차원)
```
```
결과:2
```
```
print(b[0,0])  # 배열의 원소 접근
```
```
결과:1
```
```
print(b.shape) # 배열의 차원
```
```
결과:(2, 3)
```
2. 특수한 배열의 생성

```
print(np.arange(10)) # 1씩 증가하는 1차원 배열(시작이 0부터)
```
```
## [0 1 2 3 4 5 6 7 8 9]
```
```
print(np.arange(5, 10)) # 1씩 증가하는 1차원 배열(시작이 5부터)
```
```
## [5 6 7 8 9]
```
```
print(np.zeros((2,2)))  # 영행렬 생성
```
```
## [[0. 0.]
## [0. 0.]]
```
```
print(np.ones((2,3)))  # 유닛행렬
```
```
## [[1. 1. 1.]
##  [1. 1. 1.]]
```
```
print(np.full((2,3), 5)) # 모든 원소가 5인 2*3행렬
```
```
## [[5 5 5]
##  [5 5 5]]
```
```
print(np.eye(3)) # 단위행렬
```
```
## [[1. 0. 0.]
##  [0. 1. 0.]
##  [0. 0. 1.]]
```
3. 배열의 차원 변환
```
a = np.arange(20)
print(a)
```
```
## [ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19]
```
```
b=a.reshape((4,5))
print(b)
```
```
## [[ 0  1  2  3  4]
##  [ 5  6  7  8  9]
##  [10 11 12 13 14]
##  [15 16 17 18 19]]
```
# 2.3 Numpy 슬라이싱/인덱싱
```
import numpy as np
lst = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
arr = np.array(lst)
a = arr[0:2, 0:2]
print(a)
```
```
## [[1 2]
##  [4 5]]
```
```
a = arr[1:, 1:]
print(a)
```
```
## [[5 6]
##  [8 9]]
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/c3abcd1e-ffe5-4b33-8022-fd99022baadf)

## 2.4 Numpy 연산
* 배열간 연산 가능
* +,-,*,/ 등의 연산자 사용가능
* add(),substract(),multiply(),divide()
```
import numpy as np

a = np.array([1,2,3])
b = np.array([4,5,6])

# 각 요소 더하기
c = a+b

# c= np.add(a, b)
print(c) # [-3 -3 -3]

# 각 요소 곱하기
# c = a*b
```
```
## [5 7 9]
```
```
c = np.multiply(a, b)
print(c) #[4 10 18]

# 각 요소 나누기
# c = a/b
```
```
## [ 4 10 18]
```
```
c = np.divide(a,b)
print(c) # [0.25 0.4 0.5]
```
```
## [0.25 0.4  0.5 ]
```
* dot()함수: 행렬의 곱
```
import numpy as np
arr1 = [[1,2],[3,4]]
arr2 = [[5,6],[7,8]]
a = np.array(arr1)
b = np.array(arr2)

c= np.dot(a, b)
print(c)
```
```
## [[19 22]
##  [43 50]]
```
* 모든 원소의 합: sum(), 모든 원소의 곱: prod()
```
import numpy as np

a = np.array([[-1,2,3],[3,4,8]])
s = np.sum(a)
print('sum=',a.sum()) 

# 행별/열별 연산 (axis=0/1)
```
```
## sum= 19
```
```
print('sum by row=',a.sum(axis=0))
```
```
## sum by row= [ 2  6 11]
```
```
print('mean=',a.mean())
```
```
## mean= 3.1666666666666665
```
```
print('sd=',a.std())
```
```
## sd= 2.6718699236469
```
```
print('product=',a.prod()) 
```
```
## product= -576
```
## 2.5 기본 수학함수

![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/878dc9c8-7533-426f-b4be-63025ce67fd5)

## 2.6 선형대수(벡터/행렬연산) 함수
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/9e8b05bd-cbbe-4b5f-a6cd-1126a3c9c861)
1. 벡터 연산(내적)
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/babcbee4-f2c3-4342-a654-cab00eada864)           
```
import numpy as np
x = np.array([1, 2, 3])
print(x)
```
```
## [1 2 3]
```
```
y = np.array([6, 23,-1])
print(y)
```
```
## [ 6 23 -1]
```
```
print(x.dot(y.T) )# x'y
```
```
## 49
```
```
print(x.T.dot(y) )# x'y
```
```
## 49
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/54c4d325-4cab-4b21-b516-ef241b6f6c52)
```
import numpy as np
x = np.array([[1., 2., 3.], [4., 5., 6.]])
y = np.array([[6., 23.], [-1, 7], [8, 9]])
print(x)
```
```
## [[1. 2. 3.]
##  [4. 5. 6.]]
```
```
print(y)
```
```
## [[ 6. 23.]
##  [-1.  7.]
##  [ 8.  9.]]
```
```
print(x.dot(y)) # xy
```
```
## [[ 28.  64.]
##  [ 67. 181.]]
```
```
print(y.dot(x)) # yx
```
```
## [[ 98. 127. 156.]
##  [ 27.  33.  39.]
##  [ 44.  61.  78.]]
```
3. 역행렬
```
import numpy as np
from numpy.linalg import inv
np.random.seed()
X = np.array([[1,2,3],[1,0,0],[0,0,1]])
print(X)
```
```
## [[1 2 3]
##  [1 0 0]
##  [0 0 1]]
```
```
Y = inv(X)
print(Y)
```
```
## [[ 0.   1.   0. ]
##  [ 0.5 -0.5 -1.5]
##  [ 0.   0.   1. ]]
```
```
X.dot(Y)
```
```
## array([[1., 0., 0.],
##        [0., 1., 0.],
##        [0., 0., 1.]])
```
## 2.7 난수(랜덤넘버)의 생성
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/53aaac45-f437-4ee5-93b1-009650ba5b76)
1. 균등분포에서 난수 생성
```
x = np.random.uniform(size=100)
x.reshape(20,5)
```
```
## array([[0.62283254, 0.83247702, 0.69284631, 0.36343642, 0.1194816 ],
##        [0.95766884, 0.96097382, 0.82350006, 0.11160819, 0.54375729],
##        [0.24869946, 0.92595691, 0.99723618, 0.99178697, 0.23498384],
##        [0.39983813, 0.32569314, 0.7650107 , 0.61846918, 0.36615931],
##        [0.48812842, 0.78436822, 0.68059491, 0.17950023, 0.888353  ],
##        [0.64016348, 0.70486181, 0.14406225, 0.67690893, 0.43506099],
##        [0.89071105, 0.477524  , 0.42140245, 0.0449729 , 0.3284721 ],
##        [0.08859325, 0.44517624, 0.03226408, 0.9500857 , 0.79906355],
##        [0.24693298, 0.93577942, 0.4421043 , 0.82808844, 0.83521711],
##        [0.43705478, 0.35683298, 0.24488695, 0.91222773, 0.1276007 ],
##        [0.94680193, 0.8077273 , 0.45796358, 0.86975714, 0.52794646],
##        [0.21696068, 0.36560811, 0.4285624 , 0.57030412, 0.46012208],
##        [0.85012542, 0.30934787, 0.45566465, 0.39913531, 0.21541012],
##        [0.72966978, 0.62645567, 0.18330374, 0.34446564, 0.64710839],
##        [0.9289908 , 0.05556862, 0.03368774, 0.42573986, 0.44694258],
##        [0.1867547 , 0.68780933, 0.44845544, 0.08709105, 0.99633162],
##        [0.82920243, 0.6960733 , 0.89147693, 0.79821622, 0.11935229],
##        [0.44458672, 0.665925  , 0.11769361, 0.57772073, 0.20383055],
##        [0.34587712, 0.14346508, 0.97603253, 0.99795754, 0.89759219],
##        [0.62642511, 0.98741594, 0.77529789, 0.04090993, 0.68038324]])
```
2. 정규분포
```
s = np.random.normal(0, 1, 1000)

import matplotlib.pyplot as plt
plt.hist(s)
```
```
## (array([  9.,  28.,  91., 183., 245., 219., 151.,  54.,  15.,   5.]), array([-2.95437005, -2.3291265 , -1.70388296, -1.07863942, -0.45339587,
##         0.17184767,  0.79709121,  1.42233476,  2.0475783 ,  2.67282184,
##         3.29806539]), <a list of 10 Patch objects>)
```
```
plt.show()
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/e8b44a92-75c8-4180-b9c0-f3234e4858ad)

```
```
# 3장 Pandas
* 데이터 처리와 분석을 위한 라이브러리
* 행과 열로 이루어진 데이터 객체를 만들어 다룰 수 있음
* 대용량의 데이터들을 처리하는데 매우 편리
* pandas 자료구조
  * Series: 1차원
  * DataFrame: 2차원
  * Panel: 3차원
* pandas 로딩
```
import numpy as np # 보통 numpy와 함께 import
import pandas as pd
```
## 3.1 Pandas DataFrame
* 2차원 자료구조
* 행레이블/열레이블, 데이터로 구성됨
* 딕셔너리(dictionary)에서 데이터프레임 생성
```
import pandas as pd
# 딕셔너리
data = {
    'year':[2016, 2017, 2018],
    'GDP rate': [2.8, 3.1, 3.0],
    'GDP': ['1.637M', '1.73M', '1.83M' ]
}
df = pd.DataFrame(data, index=data['year']) # index추가할 수 있음
print(df)
```
```
##       year  GDP rate     GDP
## 2016  2016       2.8  1.637M
## 2017  2017       3.1   1.73M
## 2018  2018       3.0   1.83M
```
```
print("row labels:", df.index)
```
```
## row labels: Int64Index([2016, 2017, 2018], dtype='int64')
```
```
print("column labels:", df.columns)
```
```
## column labels: Index(['year', 'GDP rate', 'GDP'], dtype='object')
```
```
print("head:", df.head()) # print some lines in data
```
```
## head:       year  GDP rate     GDP
## 2016  2016       2.8  1.637M
## 2017  2017       3.1   1.73M
## 2018  2018       3.0   1.83M
```
* csv 파일에서 데이터프레임 생성
```
csv_data_df = pd.read_csv('/home/jskim/www/lectures/data/titanic.csv')
print(csv_data_df.head())
```
```
##    Surv    N   Class    Age     Sex
## 0    20   23    Crew  Adult  Female
## 1   192  862    Crew  Adult    Male
## 2     1    1   First  Child  Female
## 3     5    5   First  Child    Male
## 4    13   13  Second  Child  Female
```
```
print(csv_data_df.columns)
```
```
## Index(['Surv', 'N', 'Class', 'Age', 'Sex'], dtype='object')
```
* 특정 변수의 추출
```
#df에서 year변수의 값 추출
print(df['year']) 
# 또는 
```
```
## 2016    2016
## 2017    2017
## 2018    2018
## Name: year, dtype: int64
```
```
print(df.year)
```
```
## 2016    2016
## 2017    2017
## 2018    2018
## Name: year, dtype: int64
```
* 부분추출
```
print(csv_data_df[['Surv', 'N']]) # DataFrame
```
```
##    Surv    N
## 0    20   23
## 1   192  862
## 2     1    1
## 3     5    5
## 4    13   13
```
```
print(csv_data_df.loc[:3, ['Surv', 'N']])
```
```
##    Surv    N
## 0    20   23
## 1   192  862
## 2     1    1
## 3     5    5
```
```
print(csv_data_df.iloc[:3, :3])
```
```
##    Surv    N  Class
## 0    20   23   Crew
## 1   192  862   Crew
## 2     1    1  First
```
```
print (csv_data_df[csv_data_df['Sex'] == 'Male']) # 부울 인덱싱
```
```
##    Surv    N  Class    Age   Sex
## 1   192  862   Crew  Adult  Male
## 3     5    5  First  Child  Male
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/5715b93b-7d37-40f5-bbc7-b32772828d7a)
* 요약
```
print(csv_data_df['N'].sum())
```
```
## 904
```
```
print (df.describe()) # describe( )를 통해 기본적인 통계치를 모두 표시
```
```
##          year  GDP rate
## count     3.0  3.000000
## mean   2017.0  2.966667
## std       1.0  0.152753
## min    2016.0  2.800000
## 25%    2016.5  2.900000
## 50%    2017.0  3.000000
## 75%    2017.5  3.050000
## max    2018.0  3.100000
```
```
print(csv_data_df.describe())
```
```
##              Surv           N
## count    5.000000    5.000000
## mean    46.200000  180.800000
## std     81.833367  380.895261
## min      1.000000    1.000000
## 25%      5.000000    5.000000
## 50%     13.000000   13.000000
## 75%     20.000000   23.000000
## max    192.000000  862.000000
```
* 빈도
```
# One-way contingency table
x=pd.crosstab(index=csv_data_df.Age, columns="count", margins=True)
print(x)
```
```
## col_0  count  All
## Age              
## Adult      2    2
## Child      3    3
## All        5    5
```
```
print('type of x=',type(x))
```
```
## type of x= <class 'pandas.core.frame.DataFrame'>
```
```
print(x['count'])
# Two-way contingency table
```
```
## Age
## Adult    2
## Child    3
## All      5
## Name: count, dtype: int64
```
```
pd.crosstab(csv_data_df.Age, csv_data_df.Sex, margins=True)
# Three-way contingency table
```
```
## Sex    Female  Male  All
## Age                     
## Adult       1     1    2
## Child       2     1    3
## All         3     2    5
```
```
pd.crosstab([csv_data_df.Age, csv_data_df.Sex], csv_data_df.Class, margins=True)
```
```
## Class         Crew  First  Second  All
## Age   Sex                             
## Adult Female     1      0       0    1
##       Male       1      0       0    1
## Child Female     0      1       1    2
##       Male       0      1       0    1
## All              2      2       1    5
```
```
## 5.2 Pandas 통계처리
```
```
df.sum()
df.sum(axis='columns')
df.mean(axis='columns', skipna=False)
df.cumsum()
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/6ff71b28-7fe0-4be2-b850-76f2dd8a54d7)

## 3.3 Pandas plot
1. Boxplot
```
df = pd.DataFrame({
         'unif': np.random.uniform(-3, 3, 20),
         'norm': np.random.normal(0, 1, 20)
    })
print(df.head())    
```
```
##        unif      norm
## 0 -0.191168  1.425540
## 1  2.634348 -0.062327
## 2 -0.562443  2.214032
## 3 -0.438013 -0.710346
## 4  0.474014 -0.519743
```
```
df.boxplot(column=['unif', 'norm'])
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/cf7c405e-cf00-4f2f-9396-922e82e16b3e)
2. time series plot
```
df.index = pd.date_range('2000', freq='Y', periods=df.shape[0])
df.plot()
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/c22679a5-8d57-49c1-aa9b-1205d624e5f7)
3. scatter plot
```
df.plot.scatter(x='unif', y='norm')
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/45b91a89-9643-40fd-a1c7-374c85c57fe3)

## 3.4 Read & write data in Pandas
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/644b11cb-d6cd-4f56-9b55-ea6099f18448)

```
pd.read_csv('data/finance.csv')
```
```
##     Age  Education        Income
## 0    54         14  66814.194580
## 1    40         12  42144.338120
## 2    35         14  25697.767150
## 3    55         12  35976.874000
## 4    40         12  39060.606060
## ..  ...        ...           ...
## 95   25         14   4625.598086
## 96   50         17  50367.623600
## 97   67         14  66814.194580
## 98   30         14  52423.444980
## 99   28         12  37004.784690
## 
## [100 rows x 3 columns]
```
# 4장  Plot using matplotlib, pandas, seaborn
## 4.1 환경설정
* 한글 폰트
* 이미지 사이즈
* sin곡선 그려보기
```
import matplotlib.pyplot as plt   # package for plotting
import numpy as np

# 그래프에서 마이너스 폰트 깨지는 문제에 대한 대처
plt.rcParams['axes.unicode_minus'] = False
# 한글폰트 전역 설정
plt.rcParams["font.family"] = 'NanumGothicCoding'#'NanumGothic'#'UnDotum'#'NanumBarunGothic' #UnDotum
# 이미지의 크기 조정
plt.rcParams["font.size"] = 12         # 그림의 글자크기 조정 11 pt
plt.rcParams["figure.figsize"] = (8,6) # 그림의 크기를 가로 7 in, 세로 5 in

x = np.linspace(-2*np.pi, 2*np.pi, 100) # -2pi과 2pi사이를 100개의 점으로 나타냄
y = np.sin(x) 
plt.plot(x,y) # 기본 플롯
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/f4cd75fb-1c3c-4cfd-a4d0-90aa98d93dc5)
## 4.2 기본 플롯
* 타이틀 / X, Y축 이름
* colors
  * b: blue; - g: green; - c: cyan; - m: magenta; - y: yellow; - k: black; - w: white
* Line style -: solid; --: dashed; -.: dash-dot; : dotted
* Symbol markers
  *.: point; ,: pixcel; o: circle; v: down trangle; ^ up-triangle; s: square
  *: star; +: +, D: diamond
* 레전드 표시
* 그리드 표시
```
plt.plot(x, y, 'r:^', label='legend 표시')                                       # color와 symbol marker type ==> 아래 참조
plt.plot(x, 0.5*y, color='blue', marker='o', linestyle=':',label='legend2 표시') # color와 symbol marker type ==> 아래 참조

plt.title('Sine graph')     # 제목, X와 Y축 제목
plt.xlabel(r'$x$')
plt.ylabel(r'$sin(4 \pi x)$')

plt.grid(True) # 그리드 표시
plt.legend(loc='upper left')
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/1d70fb53-8dec-4049-8ed1-95d34d568139)

## 4.3 Subplot
* 여러개의 그림을 행렬처럼 배치
```
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0,1,50)
y1 = np.cos(4*np.pi*x)
y2 = np.cos(4*np.pi*x)*np.exp(-2*x)

plt.subplot(2,1,1) # 2행 1열, idnum
plt.plot(x,y1,'r-*',lw=1)
plt.grid(True)
plt.ylabel(r'$sin(4 \pi x)$')


plt.subplot(2,1,2)
plt.plot(x,y2,'bo',lw=1)
plt.grid(True)
plt.xlabel('x')
plt.ylabel(r'$ e^{-2x} sin(4\pi x) $')
#plt.axis([0, 1,-1.5,1.5]) # x축 범위/y축범위
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/61c54904-dcf3-4472-b8d2-aa72de857ec7)

## 4.4 다양한 plots
1. plt.plot()
2. plt.boxplot()
3. plt.hist()
4. plt.scatter([x축 데이터], [y축 데이터])
5. plt.bar([x축 데이터], [y축 데이터])
6. plt.pie([비율 데이터])
### 4.4.1 상자그림
```
data = np.random.normal(0, 4, 100)
a = plt.boxplot(data, vert=False) # vert: 가로/세로 상자그림
plt.title('Basic Plot')
plt.show()
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/ea166646-8dfb-4bb4-ae09-d4bbdbb346f9) 
```
import seaborn as sns
iris = sns.load_dataset("iris")    # 붓꽃 데이터
#iris.columns
s1 = iris['sepal_length'].to_list()
s2 = iris['sepal_width'].to_list()
plt.boxplot([s1,s2]) # vert: 가로/세로 상자그림
```
```
## {'whiskers': [<matplotlib.lines.Line2D object at 0x7fbe332c7390>, <matplotlib.lines.Line2D object at 0x7fbe33258690>, <matplotlib.lines.Line2D object at 0x7fbe33266550>, <matplotlib.lines.Line2D object at 0x7fbe33258c10>], 'caps': [<matplotlib.lines.Line2D object at 0x7fbe33258b90>, <matplotlib.lines.Line2D object at 0x7fbe332c7550>, <matplotlib.lines.Line2D object at 0x7fbe33266f10>, <matplotlib.lines.Line2D object at 0x7fbe3325e5d0>], 'boxes': [<matplotlib.lines.Line2D object at 0x7fbe332d1410>, <matplotlib.lines.Line2D object at 0x7fbe3325eb90>], 'medians': [<matplotlib.lines.Line2D object at 0x7fbe3325e610>, <matplotlib.lines.Line2D object at 0x7fbe3326e950>], 'fliers': [<matplotlib.lines.Line2D object at 0x7fbe3325eb10>, <matplotlib.lines.Line2D object at 0x7fbe3326ee50>], 'means': []}
```
```
plt.title('Iris data')
plt.xticks([1,2], ['sepal_length', 'sepal_width'])
```
```
## ([<matplotlib.axis.XTick object at 0x7fbe332a8bd0>, <matplotlib.axis.XTick object at 0x7fbe332a8290>], <a list of 2 Text xticklabel objects>)
```
```
plt.show()
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/08742bcb-bcae-4032-9e17-0c24d932396f)
## 4.4.2 히스토그램
```
plt.hist([s1,s2], label=['sepal_length', 'sepal_width'])
```
```
## ([array([ 0.,  0.,  0.,  1., 21., 37., 36., 35., 13.,  7.]), array([19., 75., 44., 11.,  1.,  0.,  0.,  0.,  0.,  0.])], array([2.  , 2.59, 3.18, 3.77, 4.36, 4.95, 5.54, 6.13, 6.72, 7.31, 7.9 ]), <a list of 2 Lists of Patches objects>)
```
```
plt.legend()
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/eff461ac-d3ab-4110-976b-353f0e29efab)
### 4.4.3 산점도
```
plt.scatter(s1, s2, color='r')
#plt.xlabel("sepal_length")
plt.ylabel("sepal_width")
plt.xlabel("sepal_width")
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/deb2348a-c335-4f59-8b08-1b2bacfa5f86)

```
groups = iris.groupby('species')

fig, ax = plt.subplots()
for name, group in groups:
    ax.scatter(group.petal_length, 
            group.petal_width, 
            marker='o', 
            label=name)
ax.legend(fontsize=12, loc='upper left') # legend position
plt.title('Scatter Plot by matplotlib', fontsize=15)
plt.xlabel('Petal Length', fontsize=12)
plt.ylabel('Petal Width', fontsize=12)
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/ac9768b5-1ba7-4ef1-a26d-d6e6d1d7a02a)
### 4.4.4 막대그래프
```
labels = ['G1', 'G2', 'G3', 'G4', 'G5']
means = [20, 34, 30, 35, 27]

x = np.arange(len(labels))  # the label locations
rec = plt.bar(x, means, 0.5) # 막대의 두께: 0.5
plt.xticks(x, labels)
```
```
## ([<matplotlib.axis.XTick object at 0x7fbe330e2e50>, <matplotlib.axis.XTick object at 0x7fbe33181c90>, <matplotlib.axis.XTick object at 0x7fbe33181610>, <matplotlib.axis.XTick object at 0x7fbe3310fe90>, <matplotlib.axis.XTick object at 0x7fbe33099590>], <a list of 5 Text xticklabel objects>)
```
```
plt.title("bar plot", fontsize=12)
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/7cad10ba-b8a2-4891-b684-33d9fa29aff6)
### 4.4.5 원그래
```
labels = ['Frogs', 'Hogs', 'Dogs', 'Logs']
sizes = [15, 30, 45, 10]
explode = (0, 0.1, 0, 0)  # only "explode" the 2nd slice (i.e. 'Hogs')

x = plt.pie(sizes, explode=explode, labels=labels, autopct='%d',
        shadow=True, startangle=90)
plt.show()        
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/024e624b-7c83-486e-8423-c8d345e25e92)

## 4.5  seaborn 패키지 & load datasets
* seaborn패키지의 load_dataset()함수: seaborn패키지의 내장데이터를 가져옴
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt   # for plotting
import seaborn  as sns
iris = sns.load_dataset("iris")    # 붓꽃 데이터
```
* iris data의 데이터타입 확인
```
print(type(iris)) # pandas의 데이터프레임
```
```
## <class 'pandas.core.frame.DataFrame'>
```
* iris data의 데이터 컬럼속성 및 데이터 확인
```
print(iris.columns)
```
```
## Index(['sepal_length', 'sepal_width', 'petal_length', 'petal_width',
##        'species'],
##       dtype='object')
```
```
iris.head()
```
```
##    sepal_length  sepal_width  petal_length  petal_width species
## 0           5.1          3.5           1.4          0.2  setosa
## 1           4.9          3.0           1.4          0.2  setosa
## 2           4.7          3.2           1.3          0.2  setosa
## 3           4.6          3.1           1.5          0.2  setosa
## 4           5.0          3.6           1.4          0.2  setosa
```
* 팁 데이터 가져오기
```
tips = sns.load_dataset("tips")    # 팁 데이터
#flights = sns.load_dataset("flights")    # 여객운송 데이터
tips.head()
```
```
##    total_bill   tip     sex smoker  day    time  size
## 0       16.99  1.01  Female     No  Sun  Dinner     2
## 1       10.34  1.66    Male     No  Sun  Dinner     3
## 2       21.01  3.50    Male     No  Sun  Dinner     3
## 3       23.68  3.31    Male     No  Sun  Dinner     2
## 4       24.59  3.61  Female     No  Sun  Dinner     4
```
* 타이타닉호 데이터
```
titanic = sns.load_dataset("titanic")    # 타이타닉호 데이터
titanic.head()
```
```
##    survived  pclass     sex   age  ...  deck  embark_town  alive  alone
## 0         0       3    male  22.0  ...   NaN  Southampton     no  False
## 1         1       1  female  38.0  ...     C    Cherbourg    yes  False
## 2         1       3  female  26.0  ...   NaN  Southampton    yes   True
## 3         1       1  female  35.0  ...     C  Southampton    yes  False
## 4         0       3    male  35.0  ...   NaN  Southampton     no   True
## 
## [5 rows x 15 columns]
```
## 4.6  scatter plot
### 4.6.1 pandas
```
iris.plot(kind='scatter',x='sepal_length',y='sepal_width',color='red')
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/732ef6b0-b7f0-44b1-843c-48982803051a)
### 4.6.2 seaborn package
```
import seaborn as sns
import matplotlib.pyplot as plt
sns.scatterplot(x="sepal_length", y="sepal_width", data=iris, style=iris.species,
                     hue=iris.species)
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/65151bd5-d276-468c-ae89-e5f4818176a3)
## 4.7 boxplot
### 4.7.1 pandas
```
import matplotlib.pyplot as plt
import numpy as np

# Random test data
np.random.seed(19680801)
all_data = [np.random.normal(0, std, size=100) for std in range(1, 4)]
labels = ['x1', 'x2', 'x3']

fig, axes = plt.subplots(nrows=1, ncols=2, figsize=(9, 4))

# rectangular box plot
bplot1 = axes[0].boxplot(all_data,
                         vert=True,  # vertical box alignment
                         patch_artist=True,  # fill with color
                         labels=labels)  # will be used to label x-ticks
axes[0].set_title('Rectangular box plot')

# notch shape box plot
bplot2 = axes[1].boxplot(all_data,
                         notch=True,  # notch shape
                         vert=True,  # vertical box alignment
                         patch_artist=True,  # fill with color
                         labels=labels)  # will be used to label x-ticks
axes[1].set_title('Notched box plot')

# fill with colors
colors = ['pink', 'lightblue', 'lightgreen']
for bplot in (bplot1, bplot2):
    for patch, color in zip(bplot['boxes'], colors):
        patch.set_facecolor(color)

# adding horizontal grid lines
for ax in axes:
    ax.yaxis.grid(True)
    ax.set_xlabel('Three separate samples')
    ax.set_ylabel('Observed values')
    
plt.show()
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/2f69b71b-2aca-4ae0-bf29-65bf5c2bc007)

```
iris.boxplot(by='species')
```
```
## array([[<matplotlib.axes._subplots.AxesSubplot object at 0x7fbe32fb8750>,
##         <matplotlib.axes._subplots.AxesSubplot object at 0x7fbe32efe910>],
##        [<matplotlib.axes._subplots.AxesSubplot object at 0x7fbe32997910>,
##         <matplotlib.axes._subplots.AxesSubplot object at 0x7fbe3294e910>]],
##       dtype=object)
```
```
plt.show()
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/3260ecaa-0014-4909-87c2-c5273688168d)
### 4.7.2 seaborn package
```
sns.boxplot(y=iris["sepal_length"])
plt.show()
```
![image](https://github.com/shinchwon/shinchaewon.data-preprocessing/assets/153939140/35d29f5e-bdf3-4b6d-b3ff-22dad9cd6ea0)
```
```
# 5
```
```
```
```
```
```
```
```
```
```
```

