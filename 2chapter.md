# 컴퓨터그래픽스 2장

## 이번 주 수업 목표

1. 2D 그래픽스(점, 선, 사각형) 및 실습, 캐릭터 만들기
2. 그래픽스로 배너 광고를 만들 수 있다.
3. 마우스를 드래그 할 수 있다.
4. 키보드를 활용할 수 있다.
5. 프로세싱의 예제(example)를 활용할 수 있다.
6. 그래픽을 pdf로 저장할 수 있다.

## [실습] 프로세싱 기반의 배너 만들기 및 그림 넣기

1. 문자 출력하기 text()
2. 한글 출력하기
3. 글자 크기 조절 하기
4. 배너 만들기
5. [키보드 활용] 배너의 속도 조절하기
6. [인터넷 연결] 사진 넣기 및 회전
개구리 만들기, 눈사람 만들기
배너 만들기 

## 글자 출력

text("andong", 0, 50); // 문자 출력

## 크기 조절

size(800, 300);

textSize(200); // 폰트 크기

text("andong", 0, height/2);

## 이동하기
'''    
~~~
void setup() { // 한번 실행
size(800, 300);
textSize(200);
}
int i; // 정수 변수
void draw() { // 반복 됨
  text("andong", i++, 200);
}
~~~

## 배경 지우기
'''    
~~~
void draw() {
  background(0); // 검은색 배경
  text("andong", i++, 200);
}
~~~

## 색상 바꾸기

1. fill(0); // 글씨를 검은색으로
2. background(255,255,0); // 노란색 바탕
3. text("andong", i++, 200);

## 오른쪽 끝에 도착하면 왼쪽 처음부터 다시 시작

text("andong", i++, 200);
if(i>width) i=0;
}

## 왼쪽 오른쪽으로 왔다 갔다 하기
'''    
~~~
void setup() {
  size(800, 300);
  textSize(200);
}
int i, dir=1;
void draw() {
  fill(0);
  background(255,255,0);
  text("andong", i, 200);
  if(i>width) dir=-1;
  if(i<0) dir=1;
  i = i+dir;
}
~~~

## 키보드 0, 1... 9까지에 따라 속도 조절
'''
~~~
void setup() {
  size(800, 300);
  textSize(200);
}
int i, dir=1, sp=1;
void draw() {
  fill(0);
  background(255,255,0);
  text("andong", i, 200);
  if(i>width) dir=-1;
  if(i<0) dir=1;
  i = i+dir*sp;
}
void keyPressed(){
  sp = key-'0'; // 0, 1, 2... 9가 됨
}
~~~

## 한글 배너 만들기
 ### [파일]>[환경설정]>언어:한국어, 스케치에디터와 콘솔 글꼴 선택:
'''
~~~
PFont f;
void setup(){
  size(800,300);
  textSize(72);
  f = createFont("굴림",64);
  textFont(f);
}
void draw(){
  fill(0);
  background(255,50,255);
  text("안녕하세요?",10,60);
}
~~~



