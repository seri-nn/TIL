### Function (함수)

함수 def () : 무엇을 넣으면 그것이 처리되어 다시 어떤 것을 돌려주는 기능을 함 

= 입력된 매개변수를 가공하고 처리해서 반환해줌 -> 변수 값을 바꿀 때마다 함수를 새로 짤 필요가 없음

e.g.
```python
def plus(x,y):
    result = 0
    result = x + y
    return result  

hap = 0
hap = plus(100,200)
print(hap)
```
--> 300 

#### 함수의 형식과 활용
- 별도의 반환 값이 없는 함수
  - 함수를 실행한 결과, 돌려줄 것이 없는 경우에는 return문 생략 가능
  - 반환 값 없이 return만 써도 됨

- 별도의 반환 값이 있는 함수
  - 함수에서 어떤 계산이나 작동을 한 후 반환할 값이 있으면 **return 반환 값** 형식으로 표현

- 반환할 값이 2개 있는 함수
  - 반환할 값이 2개면 **return 반환 값1, 반환 값2** 형식으로 표현

  e.g.
```python
def func():
  res1 = 100
  res2 = 200

  return res1, res2

hap1, hap2 = 0, 0
hap1, hap2 = func()
print("func()에서 돌려준 값 ->", hap1, hap2) 

















 
