# java-calculator-precourse

<h2 style="border-bottom: 1px solid #21262d; color: #c9d1d9;"> 📜 과제 진행 요구 사항 </h2>

- 미션은 문자열 덧셈 계산기 저장소를 포크하고 클론하는 것으로 시작한다.

- 기능을 구현하기 전 README.md에 구현할 기능 목록을 정리해 추가한다.

- Git의 커밋 단위는 앞 단계에서 README.md에 정리한 기능 목록 단위로 추가한다.

  : `AngularJS Git Commit Message Conventions`을 참고해 커밋 메시지를 작성한다.

- 자세한 과제 진행 방법은 프리코스 진행 가이드 문서를 참고한다.

<h2 style="border-bottom: 1px solid #21262d; color: #c9d1d9;"> 🛠️ 기능 요구 사항 </h2>

### 1. **문자열 입력 처리**

- **1-1) 사용자로부터 문자열 입력**:
  - 콘솔에서 사용자가 문자열을 입력한다.
  - 입력된 문자열이 `null`이거나 빈 문자열인 경우, `0`을 반환한다.
  - **특수 상황 1**: 구분자 또는 커스텀 구분자만 입력된 경우에도 `0`을 반환한다.

### 2. **구분자 처리**

- **2-1) 기본 구분자**:
  - 기본 구분자는 쉼표(`,`)와 콜론(`:`)이다.
  - 입력 문자열에서 기본 구분자를 기준으로 숫자를 추출한다.

- **2-2) 커스텀 구분자**:
  - 문자열 앞부분에 `"//"`와 `"\n"` 사이에 위치한 문자를 커스텀 구분자로 지정할 수 있다.
  - **특수 상황 2**: 커스텀 구분자가 여러 문자(문자열)일 경우에도 커스텀 구분자로 작동하도록 한다. 예: `//***\n1***2***3`

      : 근거-(구분 문자(영어: Delimiter)는 일반 텍스트 또는 데이터 스트림에서 별도의 독립적 영역 사이의 경계를 지정하는 데 사용하는 하나의 문자 혹은 문자들의 배열이다)
  - **특수 상황 3**: 커스텀 구분자가 2개 이상일 경우에도 모두 인식하여 처리한다. 예: `//*\n//%\n1*2%3`

### 3. **숫자 덧셈 처리**

- **3-1) 숫자 추출**:
  - 구분자(기본 구분자 또는 커스텀 구분자)를 기준으로 문자열을 분리하여 숫자를 추출한다.
  - 추출된 숫자는 모두 더해 반환한다.

### 4. **예외 처리**

- **4-1) 양수 이외의 숫자 입력 시 예외 처리**:
  - 입력 문자열에 0 혹은 음수가 포함된 경우 `IllegalArgumentException`을 발생시킨다.

- **4-2) 잘못된 구분자 혹은 문자 입력 시 예외 처리**:
  - 입력 문자열의 구분자가 유효하지 않거나 잘못된 형식이거나 이외의 문자가 입력된 경우 `IllegalArgumentException`을 발생시킵니다.

<h2 style="border-bottom: 1px solid #21262d; color: #c9d1d9;"> 👩🏻‍💻 프로그래밍 요구 사항 </h2>

- JDK 21 버전에서 실행 가능해야 한다.

- 프로그램 실행의 시작점은 Application의 main()이다.

- build.gradle 파일은 변경할 수 없으며, 제공된 라이브러리 이외의 외부 라이브러리는 사용하지 않는다.

- 프로그램 종료 시 System.exit()를 호출하지 않는다.

- 프로그래밍 요구 사항에서 달리 명시하지 않는 한 파일, 패키지 등의 이름을 바꾸거나 이동하지 않는다.

- 자바 코드 컨벤션을 지키면서 프로그래밍한다.

  : 기본적으로 `Java Style Guide`를 원칙으로 한다.

- camp.nextstep.edu.missionutils에서 제공하는 Console API를 사용하여 구현해야 한다.

  : 사용자가 입력하는 값은 `camp.nextstep.edu.missionutils.Console`의 `readLine()`을 활용한다
