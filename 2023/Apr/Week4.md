# 4월 24일 월요일

- price feed 컨트랙트 Dependency injection 이슈를 해결했다.
  - 원인은 Typechain에서 index.ts에서 class가 아닌 type으로 export를 하는것이었고, 이것에 대해 Container.set이 안먹히는 이슈였다.
  - 이걸 어떻게 해결할까 했는데, TypeDI에는 class가 아닌 다른 타입? 인터페이스 같은것들도 지원할 수 있는 Token이라는 제네릭 클래스가 있었다.
  - 그래서 Token<Contract> 에 의존성을 주입하는 방식을 사용하여 해결했다. 이게 베스트 프랙티스인지는 모르겠다.
- Leetcode 589. N-ary Tree Preorder Traversal 문제 풀이를 시도했다.
  - 트리 관련된 공부를 조금 더 하고 다시 시도를 해봐야 할 것 같다.
