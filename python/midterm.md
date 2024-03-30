### Midterm 

1. 학번을 입력받아 끝자리가 5 또는 0인 경우 "안녕하세요"를 출력, 나머지는 "반갑습니다"를 출력

- 학번은 "id"라는 변수에 입력 받습니다

```python
id = int(input("학번을 입력하세요:"))
if id % 5 == 0:
  print("안녕하세요")
else:
  print("반갑습니다")
```

2. 리스트 a에 있는 원소 중 짝수의 개수를 출력

- 짝수의 개수는 "res"라는 변수를 이용

```python
a=[1,11,80,24,67,32,19,24,88]
res=0
for i in a:
  if i % 2 == 0:
    res=res+1
print(res)
```

3. 리스트 b가 주어졌을 때, 아래와 같이 출력 **

![image](https://github.com/seri-nn/TIL/assets/129299033/d100f687-a9b6-413f-b986-d5dda1a8a533)

```python
b=[1, 2, 3, 4, 5]
c=b.copy()
c.reverse()
print(c)
``` 

4. for문을 이용하여 다음의 실행결과가 나오도록 코드 구현 
![image](https://github.com/seri-nn/TIL/assets/129299033/0ad58a2f-e1d0-48b5-9b8d-aa3df4c8b568)

```python
for i in range(1,7,1):
  print((str(7-i) + '') * (7-i))
```

5. 딕셔너리 자료 구조를 이해하여 아래의 빈칸을 채워보자

```python
score={"국어":90, "영어":95, "수학":77, "미술":68, "과학":82}
sum=0
average=0.0
for i in score:
  sum += score[i]
  print("%s 과목의 점수는 %d 입니다." %(i, score[i]))
average=sum/len(score)
print("전체 평균은 %d 입니다." %average)
```

6. 6명의 학생의 점수가 있는 "score" 리스트가 있고, 70점이 넘은 학생에게 아래와 같이 합격 메시지를 출력

```python
score=[71, 55, 24, 73, 68, 90]
n=0
for i in score:
  n=n+1
  if i < 70:
    continue
  print("%d번 학생 합격" %(n))
```
  
7. 국가명의 길이가 3인 국가의 수도를 아래와 같이 출력되도록 코드 구현

```python
capital = {"대한민국":"서울", "미국":"워싱턴", "프랑스":"파리", "영국":"런던", "스위스":"베른", "베트남":"하노이", "덴마크":"코펜하겐"}
for i in capital:
  if len(i)==3:
    print("%s의 수도는 %s 입니다." %(i, capital[i]))
```

8. 주어진 리스트의 평균을 구해보자

```python
value=[80, 75, 91, 47, 66, 82, 57, 65, 90, 91, 33, 39, 78, 59, 40, 23, 19, 99, 75, 79, 37, 48, 82, 60, 60, 63, 100, 8, 12, 92, 32, 50, 61, 28, 84, 40, 100, 25, 94, 74, 88, 94, 100, 5, 26]
sum=0
for i in value:
  sum=sum+i
average=sum/len(value)
print(average)
```

9. 내가 가고 싶은 국가 리스트 중에서 친구가 가본 국가를 찾아보자

- 친구가 가본 국가 리스트 : visit
- 내가 가고 싶은 국가 리스트 : wish

```python
visit=["영국", "일본", "미국", "프랑스", "폴란드", "칠레", "캐나다", "이탈리아"]
wish=["브라질", "독일", "캐나다", "호주", "영국"]
result=[]

for i in wish:
  if i in visit:
    result.append(i)
print(result)
```



















