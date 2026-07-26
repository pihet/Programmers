# Programmers 코딩테스트 학습 기록장

> 단순히 문제 풀이 코드를 저장하는 것을 넘어, 풀이 과정에서의 아이디어, 자료구조/알고리즘 개념, 배운 점을 의미 있게 기록합니다.

---

## 최종 목표 (2달 커리큘럼)
- **최종 목표**: 2달 이내 프로그래머스 Level 3 혼자 풀기 + Level 4 도전 가능 수준 도달 (Python 알고리즘 및 SQL 동시 진행)
- **현재 수준**: 
  - Python 알고리즘: Level 1 ~ Level 2 (스택/큐 진행 중)
  - SQL: 과거 4단계까지 풀었으나 다수 망각, Lv.1~2 기초/약점 복습 후 Lv.4 재정복 예정

---

## 학습 가이드라인 & AI 멘토 규칙

- **문제 출처**: 반드시 프로그래머스(Programmers)에 실제로 존재하는 문제로 추천 및 진행합니다.
- **SQL 예시 테이블 및 결과 포함 규칙**:
  - SQL 문제를 제공하거나 노트북 노트를 세팅할 때, **지문 내에 예시로 제공되는 테이블 구조(컬럼 및 샘플 데이터)와 기대되는 최종 출력 결과 테이블**을 마크다운 표(Table) 형태로 반드시 수록합니다.
- **정답 및 뼈대 코드 최소화 규칙 (학습 주도성 보장)**:
  - 문제를 제공할 때 스타터 코드는 오직 프로그래머스 웹사이트가 기본 제공하는 수준인 **기본 함수 껍데기(`def solution(...)`)와 기본 리턴문(`return answer`)**만 제공합니다. (SQL의 경우 `SELECT` 구문 하나만 제공)
  - 내부 변수 선언, 루프 조건문 등의 코드는 절대 미리 작성해두지 않고 완전히 사용자가 빈 화면에서 짤 수 있도록 비워둡니다.
  - 대신 구현할 수 있도록 세부 설계 과정, 단계별 의사코드(Pseudocode), 논리적 흐름도 힌트를 텍스트로 풍부하게 가이드합니다.
- **입출력 예 설명 포함 규칙**:
  - 문제를 추천하거나 노트북 노트를 생성할 때, 단순히 입출력 예시 값만 적지 않고 **입출력 예시에 대한 상세한 작동 흐름 설명**을 항상 누락 없이 함께 제공합니다.
- **날짜 기반 N일차 생성 및 당일 문제 누적 규칙**:
  - `N일차.ipynb` 파일은 실제 날짜(자정 00:00 KST) 기준으로 **하루에 1개만 사용**합니다.
  - 동일한 날짜 내에서 추가 문제 요청 시 새 일차 파일(`N+1일차.ipynb`)을 생성하지 않고, **당일 전용 파일(`N일차.ipynb`) 내부 셀에 추가 문제(문제 2, 문제 3...)를 계속 이어붙여 세팅**합니다.
  - 실제로 자정이 지나서 다음날이 되었을 때만 다음 일차 파일(`N+1일차.ipynb`)을 생성합니다.
- **매일 오후 11:50 자동 Git Commit & Push 규칙**:
  - 매일 오후 11:50(23:50 KST)에 `Programmers` 폴더 내 `python` 및 `sql` 학습 파일의 변경 사항을 확인하여 자동으로 GitHub에 푸시합니다.
  - 커밋 메시지 양식: `YY.MM.DD_오늘핵심주제` (예: `26.07.22_스택큐_프로세스_주식가격_및_SQL_대여기간`)
- **수준 파악 및 동적 난이도 조절 규칙**:
  - 사용자의 문제 풀이 성공 여부, 이해도, 질문 내용, 소요 시간을 매번 분석하여 실시간 수준을 파악합니다.
  - 파악된 수준에 맞춰 다음 문제 난이도(Lv.1 기초 -> Lv.2 핵심 -> Lv.2 심화 -> Lv.3 진입)를 능동적으로 조절하여 제공합니다.
- **Jupyter Notebook (.ipynb) 무결성 및 문법 검과 규칙**:
  - `N일차.ipynb` 주피터 노트북 파일 생성 및 수정 시 반드시 JSON 규격(쌍따옴표, 쉼표 위치, source 줄바꿈 이스케이프 등)을 엄격히 준수하여 에디터 파싱 오류(`The editor could not be opened due to an unexpected error`)가 발생하지 않도록 사전 유효성 검사를 거칩니다.
- **AI 행동 지침**:
  1. 답변 및 문제 추천 전 항상 이 README.md의 학습 레벨과 지침을 최우선으로 확인합니다.
  2. 문제 추천 시 단계적 성장을 위해 개념 설명, 힌트, 실수하기 쉬운 포인트 분석을 제공합니다.
  3. 풀이 완료 후 의미 있는 배운 점, 시공간 복잡도, 핵심 쿼리 패턴을 함께 기록합니다.
  4. 답변 작성 시 이모티콘, 이모지, 아이콘 등의 특수 기호는 일절 사용하지 않습니다.

---

## 과거 SQL 학습 실수 및 약점 분석 노트 (복습용)

1. **날짜 계산 (DATEDIFF)**: `DATEDIFF(END_DATE, START_DATE)` 시 시작일 포함을 위해 반드시 `+ 1` 처리할 것.
2. **CASE WHEN 문법**: 조건 끝에 `END` 사용 필수, 컴마(`,`) 금지. 예외 조건(NULL 등)을 고려한 `ELSE` 또는 `IFNULL` 처리.

---

## 학습 현황

### Python 알고리즘 트랙
- **1일차**: 데이터 처리 기초
- **2일차**: 웹 크롤링 정리
- **3일차**: 스택/큐 - [기능개발 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/42586)
- **4일차**: 
  - 문제 1: 스택/큐 - [프로세스 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/42587)
  - 문제 2: 스택/큐 - [주식가격 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/42584)
  - 문제 3: 스택/큐 - [올바른 괄호 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/12909)
  - 문제 4: 스택/큐 - [다리를 지나는 트럭 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/42583)
  - 문제 5: 스택 - [짝지어 제거하기 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/12973)
  - 문제 6: 스택 - [괄호 회전하기 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/76502)
- **5일차**: 
  - 문제 1: 해시 - [전화번호 목록 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/42577)
  - 문제 2: 해시 - [의상 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/42578)
  - 문제 3: 해시 - [완주하지 못한 선수 (Lv.1)](https://school.programmers.co.kr/learn/courses/30/lessons/42576)
  - 문제 4: 해시 - [폰켓몬 (Lv.1)](https://school.programmers.co.kr/learn/courses/30/lessons/1845)
- **6일차**: 
  - 문제 1: 힙 - [더 맵다 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/42626)
  - 문제 2: 정렬 - [가장 큰 수 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/42746)
  - 문제 3: 정렬 - [K번째수 (Lv.1)](https://school.programmers.co.kr/learn/courses/30/lessons/42748)
- **7일차 (오늘)**: 
  - 문제 1: 정렬 - [H-Index (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/42747)
  - 문제 2: 완전탐색 - [최소직사각형 (Lv.1)](https://school.programmers.co.kr/learn/courses/30/lessons/86549)
  - 문제 3: 완전탐색 - [카펫 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/42842)

### SQL 트랙
- **1일차**: 
  - 문제 1: GROUP BY & 날짜 - [자동차 평균 대여 기간 구하기 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/157345)
  - 문제 2: CASE WHEN & 날짜 - [조건에 부합하는 중고거래 상태 조회하기 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/164672)
- **2일차**: 
  - 문제 1: JOIN - [조건에 맞는 도서와 저자 리스트 출력하기 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/144854)
  - 문제 2: JOIN & GROUP BY - [성분으로 구분한 아이스크림 총 주문량 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/133026)
- **3일차**: 
  - 문제 1: NULL 처리 - [NULL 처리하기 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/59410)
  - 문제 2: GROUP BY & HAVING - [동명 동물 수 찾기 (Lv.2)](https://school.programmers.co.kr/learn/courses/30/lessons/59041)
  - 문제 3: JOIN & DATETIME - [있었는데요 없었습니다 (Lv.3)](https://school.programmers.co.kr/learn/courses/30/lessons/59043)
- **4일차 (오늘)**: 
  - 문제 1: JOIN & ORDER BY - [오랜 기간 보호한 동물(1) (Lv.3)](https://school.programmers.co.kr/learn/courses/30/lessons/59044)

---

*단순한 코테 기록용이 아닌 의미 있는 기록장이 되길 바라며*
