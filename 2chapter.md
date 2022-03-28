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

## [실습] 빙글빙글 돌아가는 사진이 마우스가 이동하면 같이 이동
'''
~~~
PImage a;
void setup(){
size(400,400);
a = loadImage("https://pbs.twimg.com/profile_images/1150112534/jcshim640_480l_400x400.jpg");
imageMode(CENTER);
}
float f;
void draw(){
translate(mouseX, mouseY);
rotate(f);
f = f + 0.05;
image(a,0,0,width/4,height>>2);
}
~~~

## [추가] 마우스가 이동하는데로 원이 그려지는 코드
'''
~~~
void setup() {
  size(400, 400);
  //stroke(255,0,255);
  //strokeWeight(4);
  //noStroke();
}
void draw() {
  fill(0,255,0);
  ellipse(mouseX, mouseY, 80, 80);
  //println(frameRate);
}
~~~

## 원과 사각형이 겹처 커졌다가 작아졌다 하면서 빙글빙글 돌아가는 코드
'''
~~~
void setup() {
 size(400, 400);
}
float f=0;
void draw() {
  translate(mouseX, mouseY);
  rotate(f);
  scale(sin(f)+1);
  f = f + 0.05; 
  fill(255, 0, 255);
  rect(-40, -40, 80, 80);
  fill(0, 255, 0);
  ellipse(0, 0, 80, 80);
}
~~~
## 저장한 사진이 빙글빙글 돌아가는 코드
'''
~~~
PImage img;
void setup() {
  size(400, 400);
  img = loadImage("phm.jpeg");
  imageMode(CENTER);
}
float f=0;
void draw() {
  translate(mouseX, mouseY);
  rotate(f);
  scale(cos(f)+1);
  f = f + 0.05;
  image(img, 0, 0, 100, 100);
}
~~~

## hello 왼쪽에서 오른쪽으로 이동하는 프로그램
'''
~~~
void setup(){
  size(800,400);
  textSize(128);
}
int i;
void draw(){
  background(0);
  text("Hello", i+=5, 200);
  if(i>width) i=0;
}
~~~

## 안녕이 왼쪽에서 오른쪽으로 이동하는 프로그램
'''
~~~
PFont f;
  void setup() {
  size(800, 400);
  textSize(128);
  f = createFont("굴림", 128);
  textFont(f);
}
int i;
void draw() {
  background(0);
  text("안녕", i+=5, 200);
  if (i>width) i=0;
}
~~~

## "andong"이 왔다갔다 하는 코드
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

## 키보드에서 숫자를 누르면 빨라지는 코드("andong"이 왔다갔다 하는 코드)
'''
~~~
void setup() {
  size(800, 300);
  textSize(200);
}
int i, dir=1, sp=1;
void draw() {
  fill(0);
  background(255, 255, 0);
  text("andong", i, 200);
  if (i>width) dir=-1;
  if (i<0) dir=1;
  i = i+dir*sp;
}
void keyPressed() {
  sp = key-'0'; // 0, 1, 2... 9가 됨 
}
~~~











