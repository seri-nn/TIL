### Quiz

1. 1부터 10까지 홀수와 짝수를 각각 출력하시오.
```python
for i in range(1,11,1):
  if i % 2== 0:
    print("%d는 짝수입니다." %i)
  else:
    print("%d는 홀수입니다." %i)
```

2. 1부터 30까지의 수 중에 짝수거나 3의 배수인 수를 제외하고 출력하시오.
```python
i=1
while i < 31:
  if i%2==0 or i%3==0:
    i=i+1
    continue
  else:
    print(i)
    i=i+1
```

3. 입력한 숫자 내에 3,6,9가 존재할 때 쳐야할 박수의 갯수를 출력하시오.
```python
number=int(input('숫자입력:'))
clap=0
for i in range(1,number+1,1):
  for j in str(i):    # 숫자 하나하나를 문자열로 바꿔야함 **중요**  -> 한자리씩 비교하기 위해서?
    if j=='3' or j=='6' or j=='9':
      clap=clap+1
print(clap)
```

















