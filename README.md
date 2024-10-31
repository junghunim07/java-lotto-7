# 로또

## 프로젝트

- 사용자에게 로또 구매 금액을 입력 받는다
- 로또 번호 **1~45** 사이 숫자인 6개의 번호로 이루어진 로또를 발급한다
- 구매 금액만큼 발급한다
- **당첨 번호** 6개와 **보너스 번호** 1개를 입력받는다
- 당첨 내역을 출력한다
- 수익률을 출력한다

## MVP

### 로또 구매 기능

---

- [x] 사용자는 로또를 구매할 금액을 입력한다
- [x] 금액 개수만큼 로또를 발행한다
    - [x] 로또 1장의 가격은 1000원
    - [x] 로또 번호의 숫자 범위는 **1~45**사이
    - [x] 1개의 로또에는 중복되지 않는 6개의 숫자
    - [x] 로또 번호는 오름차순으로 정렬
- [x] 구매한 로또 개수를 보여준다
    - [x] 각 발행된 로또 번호들을 보여준다
  ```
  8개를 구매했습니다.
  [8, 21, 23, 41, 42, 43]
  [3, 5, 11, 16, 32, 38]
  [7, 11, 16, 35, 36, 44]
  [1, 8, 11, 31, 41, 42]
  [13, 14, 16, 38, 42, 45]
  [7, 11, 30, 40, 42, 43]
  [2, 13, 22, 32, 38, 45]
  [1, 3, 5, 14, 22, 45]
  ```

### 로또 당첨 기능

---

- [x] 로또 당첨 번호를 입력받는다
    - [x] 6개의 번호는 중복되지 않는다
- [ ] 보너스 번호 1개를 입력받는다
    - [ ] 보너스 번호는 당첨 번호와 중복되지 않는다
- [ ] 당첨은 1등~5등까지 있다
    - 1등: 6개 번호 일치 / 2,000,000,000원
    - 2등: 5개 번호 + 보너스 번호 일치 / 30,000,000원
    - 3등: 5개 번호 일치 / 1,500,000원
    - 4등: 4개 번호 일치 / 50,000원
    - 5등: 3개 번호 일치 / 5,000원
- [ ] 당첨내역을 출력한다.
    ```
    당첨 통계
    ---
    3개 일치 (5,000원) - 1개
    4개 일치 (50,000원) - 0개
    5개 일치 (1,500,000원) - 0개
    5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
    6개 일치 (2,000,000,000원) - 0개
    ```

### 수익률 계산 기능

- [ ] 수익률 = 당첨금액 / 구매 금액 * 100
- [ ] 소수점 둘째자리에서 반올림한다
    - `(ex. 100.0%, 51.5%, 1,000,000.0%)`
- [ ] 수익률을 출력한다.
  ```
  총 수익률은 62.5%입니다.
  ```

### 예외

---

- [ ] 사용자가 잘못된 값을 입력할 경우 `IllegalArgumentException`을 발생
- [ ] 모든 예외상황에서 "[ERROR]"시작한 에러 메시지를 출력하고 **그 부분부터 다시 입력을 받는다.**

#### 로또 구입 시 예외

- [x] 금액이 1000원으로 안나눠지는 경우
- [x] 문자를 입력했을 경우
- [x] 0을 입력했을 경우
- [x] 음수를 입력했을 경우

#### 당첨 번호를 입력받을 시 예외

- [x] 중복된 번호 입력할 경우
- [x] 양의 정수가 아닌 실수가 올 경우
- [x] 1 ~ 45 사이 숫자가 아닐 경우
- [x] 쉼표(,)를 제외한 다른 문자가 올 경우
- [x] 쉼표(,)가 양 사이드에 존재할 경우
- [x] 쉼표(,)가 연속으로 존재할 경우

#### 보너스 번호 입력 시 예외

- [x] 당첨 번호와 중복일 경우
- [x] 숫자가 아닌 다른 문자가 올 경우
- [x] 양의 정수가 아닌 실수가 올 경우
- [x] 하나의 숫자가 아닐 경우
- [x] 1 ~ 45 사이 숫자가 아닐 경우

- `Exception`이 아닌 `IllegalArgumentException`, `IllegalStateException` 등과 같은 명확한 유형을 처리한다.

## 프로그래밍 요구 사항

- 함수(또는 메서드)의 길이가 15라인을 넘어가지 않도록 구현한다.
- 함수(또는 메서드)가 한 가지 일만 잘 하도록 구현한다.
- else 예약어를 쓰지 않는다.
- Java Enum을 적용하여 프로그램을 구현한다.
- 구현한 기능에 대한 단위 테스트를 작성한다. **단, UI(System.out, System.in, Scanner) 로직은 제외한다.**
- 단위 테스트 작성이 익숙하지 않다면 `LottoTest`를 참고하여 학습한 후 테스트를 작성한다.