# 컴퓨터 그래픽스 1장

## □ 1주차 실습
1. 프로세싱 다운로드 및 압축 풀기, 바탕화면에 바로가기 만들기
2. 원 그리기, 색상 변경
3. 펜 만들기, mouseX, mouseY 변수
4. 원이 하늘에서 내려오기

## □ Processing 언어
1. fill, ellipse, rect
2.구조 void setup(), void draw()
3. 색상의 이해: 검정: 0,0,0 / 회색: 127,127,127 / 흰색 255,255,255
               붉은색: 255,0,0 / 초록색: 0,255,0 / 청색 0,0,255

## □ 내장변수
pmouseX, pmouseY: 마우스의 이전 지점
mouseX, mouseY: 마우스의 현재 지점
width: 화면의 폭
height: 화면의 높이
mousePressed: 마우스가 눌르면 1, 놓으면 0

##[실습1] 펜 만들기

 '''    
 ~~~
 void setup(){
  size(500,500);
  stroke(0,255,0);
  strokeWeight(16);
}
void draw(){
  if(mousePressed)
    line(pmouseX,pmouseY,mouseX,mouseY);
}
~~~

> ##[실습2] 공이 하늘에서 아래로 내려오기
'''    
~~~
void setup() { // 한번 실행
  size(400, 400); // 화면 가로 세로 크기
}
int i; // 정수 변수의 선언
void draw() { // 반복 됨
  background(0); // 배경 지우기
  ellipse(50, i++, 80, 80); // 타원그리기
}
~~~

> ##□ [실습3] 도형의 회전 실습
'''    
~~~
void setup() {
  size(500, 500);
  rectMode(CENTER);
}
float f;
void draw() {
  translate(mouseX, mouseY);
  scale( sin(f) + 1);
  rotate(f);
  f = f+0.05;
  fill(255, 0, 255);
  rect(0, 0, 80, 80);
  fill(0, 255, 0);
  ellipse(0, 0, 80, 80);
}
~~~





​
