#실행 컨텍스트와 클로저

**실행 컨텍스트의 개념**
실행 컨텍스트란 실행 가능한 자바스크립트 코드 블록이 실행되는 환경이다.
`현재 실행되는 컨텍스트에서 이 컨텍스트와 관련 없는 실행 코드가 실행되면, 새로운 컨텍스트가 생성되어 스택에 들어가고 제어권이 그 컨텍스트로 이동한다.`

**실행 컨텍스트 생성 과정**
**활성 객체 생성**
실행 컨텍스트가 생성되면 자바스크립트 엔진은 해당 컨텍스트에서 실행에 필요한 여러 가지 정보를 담을 객체를 생성한다. 이를 활성 객체라 한다.
매개변수, 사용자 정의 변수 및 객체를 저장하는 용도도 담겨있다.

**arguments 객체 생성**
활성 객체는 arguments 프로퍼티를 통해 arguments 객체를 참조한다.

**스코프 정보 생성**
현재 컨텍스트의 유효 범위를 나타내는 스코프 정보를 생성한다.
실행 컨텍스트 안에서 연결 리스트와 유사한 형식으로 만들어진다.
현재 컨텍스트에서 특정 변수에 접근해야 할 경우, 이 리스트를 활용한다.
이 리스트를 스코프 체인이라 하며 [[Scope]] 프로퍼티가 참조된다.

**변수 생성**
현재 실행 컨텍스트 내부에서 사용되는 지역 변수의 생성이 이루어진다.
변수는 메모리에 생성되고 초기화되는데
먼저 변수가 생성되며 undefined가 할당된다.
그 후 변수에 초기화 작업이 있다면 그 과정을 진행한다.

**this 바인딩**


**활성 객체의 순서**
1. arguments 프로퍼티
2. 스코프 체인
3. 지역 변수 생성 및 초기화
4. this 바인딩
5. 코드 실행

**코드 실행**
전역 실행 컨텍스트는 일반적인 실행 컨텍스트와는 약간 다른데, arguments 객체가 없으며, 전역 객체 하나만을 포함하는 스코프 체인이 있다.

**스코프 체인**
자바스크립트는 오직 함수만이 유효 범위의 한 단위가 된다.
이 유효 범위를 나타내는 스코프가 [[Scope]] 프로퍼티로 각 함수 객체 내에서 연결 리스트 형식으로 관리된다.
각각의 함수는 [[Scope]]프로퍼티로 자신이 생성된 실행 컨텍스트의 스코프 체인을 참조한다.
이 실행 컨텍스트는 실행된 함수의 [[Scope]] 프로퍼티를 기반으로 새로운 스코프 체인을 만든다.

실행 컨텍스트는 스코프 체인을 통해 식별자 인식이 이루어진다.
this는 스코프 체인의 참조 없이 접근할 수 있다.

**함수의 호이스팅**
함수가 자신이 위치한 코드에 상관없이 함수 선언문 형태로 정의한 함수의 유효 범위는 코드의 맨 처음부터 시작한다. - 뺴박켄트..
변수 또한 호이스팅 되나 그 값은 호이스팅 되지 않는다.
함수 객체가 생성될 때, 그 함수 객체의 [[Scope]]는 현재 실행되는 컨텍스트의 변수 객체에 있는 [[Scope]]를 그대로 가진다.

**클로저**
이미 생명 주기가 끝난 외부 함수의 변수를 참조하는 함수를 클로저라 한다.
이 때 클로저로 참조되는 함수를 자유 변수라 한다.



**실행 컨텍스트와 스코프 체인**
1. 더 정리해야 할 것..
2. 연결 리스트 자료구조 설명 및 구현


