# ⭐Markdown 익히기
## 0. Markdown이란? 
Markdown은 마크업 정보를 표현하는 언어이다.

마크업 정보는 문서의 포맷, 내용 찾아보기 작업 방법, 내용 중의 요소와 같은 문서 또는 다른 문서 중의 다른 요소와의 연결을 지정한다. 더 쉽게 말해 문서 내용에 대한 정보가 아니라 문서에 대한 내용이 어떻게 배치되는 지에 대한 정보이다. 

Markdown을 통해서 설치방법, 소스코드 설명 등을 간단하게 기록하고 가독성을 높일 수 있다는 강점이 있고 많은 사람들이 Github의 Repository에 관한 정보를 기록하는 README.md가 markdown 문서이다. 
## 1. Header(제목)
Header는 문자 앞에 '#'이나 을 입력하면 된다. (단, #과 한 칸을 띄워야지만 적용)

'#'의 갯수에 따라 문자의 크기를 조절할 수 있다. '#'는 최대 6개까지 사용 가능하다. 

![# 제목](https://github.com/seri-nn/TIL/assets/129299033/2aaf55c1-d1db-42c5-bd3a-93782bc64fcb)
<img src='https://github.com/seri-nn/TIL/assets/129299033/8483ce0c-bd84-4957-b4c4-24e7673c7a4e' img width='10%' hegith='20%'></img>
## 2. Line Feed(줄 바꾸기)
줄 바꾸기를 할 때는 enter를 2번 해야한다. 

![줄바꾸기 입력](https://github.com/seri-nn/TIL/assets/129299033/f8a5c82b-649b-4349-a894-3addf55afdb0)
![줄바꾸기 결과](https://github.com/seri-nn/TIL/assets/129299033/a0aa0099-d9da-4d5a-afff-ef1036cca3fa)
## 3. Indexing(순서)
평소에 순서를 매기는 방법과 동일하다. 들여쓰기를 하면 순서가 매겨지지 않는다. 

1. 첫번째
2. 두번째
   - 순서 적용 안됨
3. 세번째
   - 순서 적용 안됨

순서가 적용되지 않는 목록에서 사용 가능한 기호
- hyphen(대쉬)
* asterisks(별표)
+ plus sign(더하기)

혼합해서 사용하는 것도 가능하다.
- 안녕
   - 안녕
     + 안녕
       * 안녕

들여쓰기를 하지 않으면 똑같은 기호로 출력되지만 들여쓰기를 했을 때는 -,+,* 어떤 것을 사용해도 다 다른 기호로 출력이 된다. 하지만 모양은 3개만 존재하는 듯
## 4. Division Line(구분선)
'-'나 '*'을 3개 이상 사용하면 된다. 중간에 띄어쓰기를 해도 되고 6개 이상 사용해도 가능하다. 

![image](https://github.com/seri-nn/TIL/assets/129299033/f91bdae2-e790-4723-ac8f-d7745d22092e)
![image](https://github.com/seri-nn/TIL/assets/129299033/0189f8a8-5912-4e13-8f1b-926ed93cf086)
## 5. Empahasis(강조)
이테릭체 : _underscore(언더바)_ or *asterisks(별표)*

굵게 : __underscore(언더바2개)__ or **asterisks(별표2개)**

굵은 이테릭체 : ___underscore(언더바3개)___ or ***asterisks(별표3개)***

취소선 : ~tilde(물결)~ 

문장 가운데에 사용할 경우에는 **asterisks**를 사용하는게 좋다. 
## 6. Quote(인용)
'>'를 사용해 인용문을 삽입할 수 있다.

인용문 안에 또 다른 인용문을 삽입하려면 '>'의 갯수를 늘리면 된다. 

인용문 안에서 다른 마크다운 요소 포함 가능하다. 

![인용문입력](https://github.com/seri-nn/TIL/assets/129299033/fedb9d2a-37ab-4fbe-9ead-2fd2e8a7c2f2)
<img src='https://github.com/seri-nn/TIL/assets/129299033/0e8f25d1-c4e9-4cd5-b1f5-5a74599b6fa5' img width='15%' height='25%'></img>
## 7. Code(코드)
1. 코드 앞 부분에 4칸(들여쓰기)을 띄워주고 위 아래로 한 줄씩 띄워준다. 안 띄워주면 적용이 안된다.
 
   들여쓰기가 적용된 부분은 다 코드블럭으로 출력되고 들여쓰기를 하지 않은 행을 만날 때까지 계속 적용된다. 

밑의 줄은 코드이다.

    This is a code block.

코드 끝

2. 코드블럭 위 아래로 '```'를 써주는 방법이다. 이때의 `는 ~ 표시 키에 있는 것을 사용한다.  

   '```' 뒤에 python이나 java 등 프로그래밍 언어를 함께 지정하면 해당 언어에 맞는 형태로 표시된다.

```python
print('hello World')
```
## 8. Hyperlink(하이퍼링크)
1. <링크주소> : 링크주소가 그대로 화면에 나타나고 누르면 해당 주소로 이동한다.
2. [링크 텍스트](링크주소) : 링크 텍스트 부분만 나타나며 텍스트를 누르면 괄호에 입력한 주소로 이동한다.
3. [링크 텍스트](링크주소, '부가설명') : 링크 텍스트 부분만 나타나며 링크 텍스트 위로 커서를 올렸을 때 부가설명이 말풍선 형태로 나타나다. 

<img src='https://github.com/seri-nn/TIL/assets/129299033/3c8a7fd9-6808-477d-bfbd-24d2d7fb8f83' img width='55%' height='45%'></img>

<https://www.naver.com/>

[NAVER](https://www.naver.com/)

[네이버](https://www.naver.com/, '네이버 홈')
## 9. Image(이미지)
![이미지 텍스트](이미지 링크주소) 형태로 이미지를 삽입할 수 있다. 

이미지 크기 조절 기능은 따로 없기 때문에 
![image](https://github.com/seri-nn/TIL/assets/129299033/d8582498-54b1-48cd-8c11-1afa0d76880d)
를 이용한다. 
