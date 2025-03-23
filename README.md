# Dart (1/2)

# Dart 언어 문법 정리

## 주석
```dart
// 한 줄 주석

/* 
   여러 줄 주석 
*/

/**
 * 여러 줄 주석 
 */
```

## 변수
```dart
var name = '홍길동';
 일반 변수
var name = '홍길동';
String city = '서울';

타입 추론
var age = 20;

※ final과 const의 차이점 : final은 동작중에 값이 고정되나 const는 컴파일 시점에서 값이 고정 됨
// final: 변경 불가능 (런타임에 결정)
final a = 2;

const: 컴파일 타임 상수
const b = 3;
```
## 연산자
```dart
 산숭 연산자
+   // 더하기
-   // 빼기
*   // 곱하기
/   // 나누기 (double)
/~  // 나누기 (int)
%   // 나머지

비교 연산자
==   // 같음
!=   // 같지 않음
>    // 큼
<    // 작음
>=   // 크거나 같음
<=   // 작거나 같음

논리 연산자
&&  // AND
||  // OR
!   // NOT
```

# 실습

## 구구단 출력
```dart
void main() {
  for (int i = 2; i <= 9; i++) {
    print('📌 ${i}단');
    for (int j = 1; j <= 9; j++) {
      print('$i × $j = ${i * j}');
    }
    print(''); 
  }
}

```

## 다양한 정사각형 출력
```dart
import 'dart:io';

void main() {
    var n=10;

  print('\n 꽉 찬 사각형');
  for (int i = 0; i < n; i++) {
    print('*' * n);
  }

  print('\n 테두리 사각형');
  for (int i = 0; i < n; i++) {
    if (i == 0 || i == n - 1) {
      print('*' * n);
    } else {
      print('*' + ' ' * (n - 2) + '*');
    }
  }

  print('\n 대각선 사각형');
  for (int i = 0; i < n; i++) {
    String line = '';
    for (int j = 0; j < n; j++) {
      line += (j == n - i - 1) ? '*' : ' ';
    }
    print(line);
  }

  print('\n 대각선 사각형');
  for (int i = 0; i < n; i++) {
    String line = '';
    for (int j = 0; j < n; j++) {
      line += (j == i) ? '*' : ' ';
    }
    print(line);
  }

  print('\n 표시 사각형');
  for (int i = 0; i < n; i++) {
    String line = '';
    for (int j = 0; j < n; j++) {
      if (j == i && j == n - i - 1) {
        line += '*'; // 가운데 X
      } else if (j == i) {
        line += '*';
      } else if (j == n - i - 1) {
        line += '*';
      } else {
        line += ' ';
      }
    }
    print(line);
  }
}

```

## 년/월/일을 입력하면 요일을 출력하라
```dart
void main() {
  var input = '2025-03-11'; // 입력 문자열
  DateTime date = DateTime.parse(input); // 문자열을 날짜로 변환

  // 요일 배열 
  List<String> weekdays = ['월', '화', '수', '목', '금', '토', '일'];

  String weekday = weekdays[date.weekday - 1]; 

  print(weekday);         
}

```
