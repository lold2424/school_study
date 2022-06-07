# 9장 Bash 쉘 스크립트

Bash = 쉘 

명령어 및 유틸리티들을 적절히 사용하여 작성한 쉘에서 동작하는 프로그램

- 리눅스, 맥 OS X 등의 운영 체제의 기본 쉘
- Bash 문법은 본 쉘의 문법을 대부분 수용하면서 확장
- 시작 파일(start-up file) <- (시스템 환경설정)

**경로에서 . 이 있는 파일은 숨겨져 있는 파일임**

- **/etc/profile** (시스템시작 파일)

전체 사용자에게 적용되는 환경 설정, 시작 프로그램 지정

- **/etc/bashrc** (시스템시작 파일)

전체 사용자에게 적용되는 별명과 함수들을 정의

- **~/.bash_profile (사용자시작 파일)**

각 사용자를 위한 환경을 설정, 시작 프로그램 지정

- **~/.bashrc (사용자시작 파일)**

각 사용자를 위한 별명과 함수들을 정의

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled.png)

### Alias 명령어 - 문자열이 나타내는 기존 명령에 대해 새 이름을 별명 정의

- Alias 이름 = 문자열
- Alias - 별명 리스트
- Unalias 단어 별명 해제

- 예제
    
    ![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%201.png)

### History 명령어 - 입력된 명령들을 기억하는 기능

- History [rh][번호]
- Histsize = 100 히스토리의 크기 100
- Histfilesize = 100 로그아웃 이후에도 저장

- 예제
    
    ![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%202.png)
    

### 재실행

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%203.png)

### 변수 - **하나의 값만 저장 가능한 변수**

- **변수이름=문자열**

**(띄어쓰기 사용 하면 안됨)**

- 변수 값 사용
- 변수에 다른값 대입 가능
- 한 번에 여러 개 변수 생성
- 한글 문자열 값 사용
- 따옴표 사용시 여러 단어 저장 가능

- 예제
    
    ![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%204.png)
    

### 리스트 변수 - **한 변수에 여러 개의 값을 저장할 수 있는 변수**

- **이름=(문자열 리스트)**
- {name[*]} 과 {name[@]}는 모든 원소 출력
- {#name[*]} 과 {#name[@]}는 개수 출력

- 예제
    
    ![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%205.png)
    

### 표준입력 읽기 - 표준입력에서 한 줄을 읽어서 단어들을 변수들에 순서대로 저장

- **read 변수1 ... 변수n**
- 마지막 변수에 남은 단어들 모두 저장

- 예제
    
    ![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%206.png)
    

### 쉘 변수

- 환경 변수와 지역변수
- 환경 변수 값 > 자식프로세스 (상속)
- 지역 변수는 불가능

- 예제
    
    ![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%207.png)
    

### 사전 정의 환경변수

아래의 것들은 미리 의미가 정해진 환경변수들이다.

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%208.png)

- 예제
    
    ![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%209.png)
    

### 사전 정의 지역 변수

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2010.png)

- 예제
    
    ![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2011.png)
    
    ![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2012.png)
    

## Bash 쉘 스크립트

- 쉘 스크립트는 명령어 및 유틸리티들을 적절히 사용하여 작성한 프로그램이다.
- 사전 정의 지역 변수로 $$, $0, $1 ~ $9, $*, $#등이 있다.
- Bash 쉘은 조건, 스위치, 반복 등을 위한 제어구조로 if, case, for, while등의 문장을 제공한다.
- Bash 쉘의 식은 비교 연산, 파일 관련 연산, 산술 연산 등을 할 수 있다.

### 쉘 스크립트 - 명령어 및 유틸리티들을 적절히 사용하여 작성한 프로그램

첫 줄에 사용할 쉘을 지정

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2013.png)

이 외에도 bash 대신 csh ,ksh, sh등이 있다.

### Bash - 리눅스, 맥 OS X 등의 운영 체제의 기본 쉘

Bash 문법은 본 쉘의 문법을 대부분 수용하면서 확장

### Bash 스크립트 작성 및 실행 과정

1. 에디터를 사용하여 Bash 스크립트 파일 작성

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2014.png)

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2015.png)

1. chmod를 이용하여 실행 모드로 변경

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2016.png)

1. 스크립트 이름을 타이핑하여 실행

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2017.png)

## if문

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2018.png)

if-then-else구문

### 비교 연산

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2019.png)

### 문자열 비교 연산

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2020.png)

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2021.png)

### 파일 관련 연산

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2022.png)

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2023.png)

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2024.png)

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2025.png)

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2026.png)

### 부울 연산자

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2027.png)

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2028.png)

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2029.png)

### 산술 연산자

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2030.png)

### 중첩 조건문

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2031.png)

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2032.png)

### 스위치

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2033.png)

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2034.png)

### 반복문 for

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2035.png)

![Untitled](https://github.com/lold2424/school_study/blob/main/Linux/Ubuntu/9%EC%9E%A5%20Bash%20%EC%89%98%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8/Untitled%2036.png)
