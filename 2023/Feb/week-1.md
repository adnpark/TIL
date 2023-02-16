### 1월 30일 월요일

- 회의와 모임이 많아서 별다른걸 못했다.
- RACE-14 성적 결과가 나왔다.
  - 나만 못본거였다. 다른 사람들의 성적은 꽤 높았다... 기분이 썩 좋지는 않다.
  - 다음번에 더 잘해보자.

### 1월 31일 화요일

- Canto 해커톤 준비를 위해 Canto 생태계에 대한 설명을 쭉 봤다.
  - 아직도 NOTE의 존재 의의에 대해서는 솔직히 물음표가 띄워지지만, CSR과 같은 개념은 매우 신박하다고 생각한다.
  - 그리고 앞으로 앱체인에 대한 수요가 가속화될수록 이더리움과 같은 기존 블록체인에서도 CSR과 유사한 컨셉을 도입하려고 시도하지 않을까.
- Perpetual DEX 생태계에 대해서 리서치를 했다.
  - 일단 완전히 다 이해를 한건 아니지만 대략적으로 얼개는 잡았다.
  - 디스프레드의 Earl님 블로그 글이 굉장히 도움이 많이 됐다.
  - 우선 gmx와 같은 오라클 모델부터 파보면 좋을것 같다.

### 2월 1일 수요일

- JS의 forEach는 동기함수이다. 즉 synchronous function이며, promise를 기다려주지 않는다.
  - 따라서 forEach의 콜백함수를 비동기함수를 집어넣어봐야 의미가 없다.
- ## 순서가 상관없는 여러개의 비동기 로직을 처리할 때는 Promise.all을 쓰는게 좋다. [참고자료](https://code-masterjung.tistory.com/91)
- 삼항연산자는 언제 사용해야 하는가?
- 메모리 변수를 활용하는 경우 해당 프로세스가 죽었을 때 어떤 사이드 이펙트가 발생할 수 있을지 항상 염두에두자.

### 2월 2일 목요일

- `__dirname`은 전역 변수로 현재 실행하는 파일의 디렉터리 경로이다. 비슷한 예시로 `__filename`이 있다. 이건 파일 이름까지 포함된 절대 경로.
- node -r tsconfig-paths/register -r ts-node/register 옵션
  - 전자는 tsconfig의 alias로 사용되는 것들의 파일 경로를 절대 경로로 변환해준다.
  - 후자는 typescript 파일을 트랜스파일하여 사용할 수 있도록 해준다.
- typeORM Migration 세미나를 준비하면서 많은걸 배웠다.
  - migration:generate는 해결되지 않은 이슈가 있다. 따라서 create를 사용하자.
- Canto CSR yield optimizer 작업 시작
  - CSR 컨트랙트 구조가 너무 확장성이 없는 형태로 짜여졌다.
  - DeFi 친화적이지가 않다... 위임하고 이런 구조가 상당히 어렵다.
  - 정확히는 CSR 보상을 특정 컨트랙트가 얼마를 받았는지를 정확히 트래킹하기가 어렵다. 특히나 assign 처럼 위임을 한 경우에는...
  - 일단 작업을 하고, CSR 컨트랙트 개선안도 함께 내보면 좋을것 같다.

### 2월 3일 금요일

- TypeORM Migration 세미나를 진행했다. 매우 즐거운 경험이었다.

### 2월 4일 토요일

- Perpetual DEX와 관련한 개념들을 살펴봤다.
  - 아직 무기한 선물에 대한 개념이 아리송하다.
  - GMX 코드도 같이 보면서 개념을 계속 잡아가면 좋을듯하다.
- DankSharding 관련 포스트들도 많이 읽어봤다.
  - Dank가 Dankrad라는 사람 이름에서 따온거였다니..
  - 아직 메커니즘이 완벽히 이해되지는 않았다. 한번 또 딥다이브 해보면 좋을듯

### 2월 5일 일요일

- Canto 해커톤 컨트랙트 작업을 했다.
  - 내 생각처럼 잘되지 않는다.
  - 막히는 부분이 많아서 답답하다.