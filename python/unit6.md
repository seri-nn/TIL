### 문자열 

#### 문자열 : 큰 따옴표, 작은 따옴표로 표현 

- 리스트와 비슷
  - 리스트는 대괄호로 묶고 문자열은 작은(큰) 따옴표로 묶어 출력

e.g.
```python
a = [1, 2, 3, 4, 5]
print(a[0])
# 1

b = "파이썬프로그래밍"
print(b[0])
# 파
```

#### 문자열 기본
- 덧셈 연산자

e.g.
``` python
a = "파이썬" + "프로그래밍"
print(a)
# 파이썬프로그래밍 
```

- 곱셈 연산자

e.g.
```python
b = "안녕"
print(b*3)
# 안녕안녕안녕 
```

#### 문자열 함수 
- len() : 리스트나 문자열의 개수를 셀 때 사용 (띄어쓰기도 포함)

e.g.
```python
a = "hello everyone"
print(len(a))
# 14

```python
a = "hihihi"
for i in range(0, len(a)):
    print(a[i], end='') # end='' 는 값을 붙여서 출력해줌. 안하면 다음 행으로 넘어가서 다 따로 출력됨 
# hihihi
``` 

- .upper() : 대문자로 바꿈
- .lower() : 소문자로 바꿈
- .swapcase() : 대소문자를 서로 바꿈
- .title() : 맨 첫 글자만 대문자로 바꿈

출력값이 TRUE / FALSE 인 함수들 

- .islower() : 소문자로 구성됐는지 확인 (다 소문자면 TRUE)
- .isupper() : 대문자로 구성됐는지 확인 (다 대문자면 TRUE) 
- .isdigit() : 숫자로 인식될 수 있는지 확인 (숫자 있으면 TRUE)
- .isspace() : 공백으로만 구성돼있는지 확인 (공백으로만 구성이면 TRUE)

#### 문자열 찾기 함수
- .count() : (" ") 괄호 안의 문자가 **몇 번** 나오는지 셈

  찾은 문자가 존재하지 않으면 -1 출력
  
e.g.
```python
word = "파이썬 재미 없어서 파이썬 짜증나 파이썬"
print(word.count("공부"))
# 2
```

-.find("문자열", 시작 index, 끝 index) : (" ") 괄호 안의 문자가 **몇 번째**에 나오는지 셈 

e.g.
```python
x = "파이썬 재미 없어서 파이썬 짜증나 파이썬"
print(x.find("재미"))
# 4 -->  띄어쓰기까지 포함해서 셈

print(x.find("파이썬"))
# 0 --> 제일 먼저 나오는 것부터 셈

print(x.find("파이썬", 1))
# 10 --> 시작 index 뒤부터 세기 시작

print(x.find("파이썬", 1, 10))
# -1 --> 시작 index 뒤부터 ~ 끝 index 전까지 셈
```

- .rfind() : 똑같이 왼->오 순서로 세는데 왼쪽이 아니라 오른쪽 쪽에서 가장 먼저 나오는 문자가 몇 번째인지 셈 

e.g.
```python
x = "파이썬 재미 없어서 파이썬 짜증나 파이썬"
print(x.rfind("증나"))
# 16 

y = "나는 공부가 너무 재미있어서 공부도 공부만 하고 싶어요"
print(y.rfind("공부"))
# 20
```

- .index() : find와 똑같이 괄호 안의 문자가 몇 번째에 나오는지 셈

  찾는 문자가 존재하지 않으면 error 발생
  
  find 함수는 문자열만 가능하지만 index함수는 리스트, 튜플에서 사용 가능 (딕셔너리는 둘 다 사용 x)

e.g.
```python
list = ["나는", "파이썬", "공부가", "좋아요"]
print(list.index("공부가"))
# 2
``` 

#### 문자열 공백 삭제, 변경 
- .strip() : 양 끝의 띄어쓰기 제거
- .lstrip() : 왼쪽 띄어쓰기 제거
- .rstrip() : 오른쪽 띄어쓰기 제거

e.g.
```python
word = " hello my name is "
print(word.strip())
# hello my name is
```

- .replace(" ", " ") : ("기존 문자", "바꿀 문자") 문자를 바꿔줌

e.g. 
```python
word = "hello my name is"
print(word.replace("hello", "hi")
# hi my name is
```

#### 문자열 분리, 결합
- .split() : 괄호 안의 값 기준으로 분리해서 리스트로 출력

e.g.
```python
word = "hello my name is"
print(word.split()) # 공백 기준으로 
# ["hello", "my", "name", "is"]
print(word.split()[0])
# hello

x = "사과, 배, 바나나, 감자"
print(x.split(","))
# ["사과", "배", "바나나", "감자"]
print(x.split("과"))
# ["사", "배, 바나나, 감자"]
```

- .join() : 리스트를 문자열로 가져오고 .앞부분은 문자열을 연결할 것

e.g.
```python
a = ["사과", "포도", "수박"]
x = ''.join(a) # 공백은 다 붙여서 출력
print(x)
# 사과포도수박

x = '-'.join(a)
print(x)
# 사과-포도-수박

















  
