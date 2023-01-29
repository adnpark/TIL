### Mon, Jan 23

- 주로 휴식
- 사이드 프로젝트 주제 탐색

### Tue, Jan 24

- TypeORM Migration
  - Migration 기능에 대해 탐색해봤음
  - 기본적으로 데이터베이스의 버전관리를 가능하게 해줌
  - 얼른 도입해야 되겠다는 생각이 많이 들었음. 지금처럼 synchronize 옵션 켜두는것은 매우 위험한 느낌
  - 다만 Migration에서 스키마 변경과 동시에 데이터 insert가 가능한지? (아마 가능할거같음) 그리고 이러한 경우 down, 즉 revert를 위한 메소드는 어떻게 해야 하는지 감이 잘 안옴
  - generate command를 사용하는건 권장되지 않는다는데 이건 조금 더 탐색이 필요할듯
- 사이드 프로젝트 주제 탐색 및 변경
  - 여러가지 생각과 고민을 하다가 결국 내가 그냥 제일 만들고 싶은거를 만들기로 함
  - Open Web3 AD Protocol을 만드려고 함.
  - 목적은 Web3 생태계에서의 오픈된 광고 프로토콜을 만드는것.
  - 누구나 퍼포먼스 마케팅을 할 수 있고, 여기에 참여하는 참가자들은 기여에 따라 보상을 얻게됨
  - 오픈된 API를 열어서 여러 월렛과 쉽게 통합될 수 있도록 하려고 함
- 알고리즘 강의 재개
  - 다시 강의 재개함. 빨리 코드 두들겨보면서 해보면 좋을듯
  - 자주 마주치게 되고, 자주 사용하게 되는 알고리즘 위주로 빠르게 배워보면 좋을듯
  - 강의에서는 파이썬으로 하는데, 나는 그냥 타입스크립트로 해보자.
- 솔리디티 강의 교안
  - 강의를 어떻게 만들면 좋을지 끄적여봤음
  - 당장 내일부터 강의 컨텐츠 제작할 예정. 일단 시작을 하자. 일단 해보자.
- Solidity 101 읽기
  - 37~46 읽음
  - 대부분 알고 있던 개념을 다시 확인하는 느낌이었음
  - address에는 명시적으로 두가지 타입이 있다는걸 알게됨
    - address, address payable
    - 그리고 address payable에는 transfer와 send라는 member가 추가적으로 있다.
    - _그래서 type conversion이 필요했던것! `payable(address)`_

### Wed, Jan 25

- 알고리즘 강의 재개
  - Linear Search 알고리즘 Typescript로 구현해봄
  - 내일은 Binary Search 구현해보자.
- 사이드 프로젝트
  - 그냥 원래 하던거 일단 하기로 함... 어차피 토이 프로젝트 느낌처럼 배우는것에 더 의미가 있었으니까
  - solidity에서 string은 length 멤버가 없다는걸 알게됨! 그래서 bytes로 변환해서 length를 계산해야 함
  - 문제는 string의 문자가 무엇이냐에 따라 bytes로 변환시에 length가 달라질 수 있음! (특수 문자인 경우 3개의 바이트로 표현될수도 있다!)
  - 따라서 정확한 string의 length를 얻기 위해서는 이를 반드시 고려해야함!
- Solidity 101
  - 58~61
  - bytes and string
    - 둘 다 특수한 형태의 array임
    - string은 bytes와 동일하지만 length나 index로 접근 불가능
    - Use bytes for arbitrary-length raw byte data and string for arbitrary-length string (UTF-8) data
    - bytes가 byte[]보다 효율적임. bytes[]는 element 사이에 31 padding bytes를 추가하기 때문.
    - 물론 길이를 완전히 특정할 수 있다면 bytes1 to bytes32를 쓰는게 좋다.
  - Memory Arrays
    - storage와 다르게 memory array는 size를 다시 설정할 수 없음
    - 따라서 .push member function 사용 불가능함
    - 그래서 memory에서 array를 다루려면 미리 필요한 size를 지정해주거나, 모든 element를 새로운 memory array에 복붙하는 수 밖에 없음

### Thu, Jan 26

- 주로 이슈 대응을 했다.
- SQL 쿼리 짤일이 있었는데, 여전히 기본기가 안잡혀있는 느낌이다. SQL 쿼리에 익숙해지는 연습이 필요하다.
- Solidity 101
  - 55~57
  - Data location 다시 개념 정리했다.

### Sun, Jan 29

- RACE-14 에 응시했다.
  - 너무 어려웠다. 처참히 깨졌다.
  - 이번 문제는 개념만 알아서 될게 아니라 DeFi 관련 실제 코드를 많이 봤어야 쉽게 풀 수 있는 문제들이 많았다.
  - 실제 프로덕션 코드를 많이 접해보는 경험이 필요해보인다.
