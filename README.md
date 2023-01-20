[SOLID Principles in TypeScript](https://medium.com/@hellokevinvogel/solid-principles-in-typescript-153e6923ffdb) article published on Medium.

## 단일 책임 원칙 Single Responsibility Principle (SRP)

- 코드 속 책의 정보 보관과 책 정보 저장 두개의 책임이 있어서 두개의 클래스로 분리한 것 같다.
- 만약 내가 리펙토링을 해야한다면 책 객체와 책을 관리하는 두 객체로 분리하는 방법을 생각해보았다.

```
export class Book {
  public title: string;
  public author: string;
  public description: string;
  public pages: number;

  // constructor and other methods

  public saveToFile(): void {
    // some fs.write method to save book to file
  }
}

export class BookManager {
  saveToFile(): Book {};
  updateToFile(): boolean {};
  deleteToFile(): boolean {};
  readToFile(): Book[] {};

}

```

## 개방 폐쇄 원칙 Open-Close Principle (OCP)

- bad 코드는 도형이 하나 늘어날 때마다 AreaCalculator 클래스의 수정이 발생한다.
- good 코드의 인터페이스를 통해 새로운 도형 객체를 선언해도 선언된 도형이 외 다른 수정이 필요하지 않다.

## 리스코프 치환 원칙 Liskov Substitution Principle (LSP)

- 부모 객체를 호출하는 동작에서 자식 객체가 부모 객체를 완전 대체할 수 있어야 한다.

## 인터페이스 분리 원칙 Interface Segregation Principle

- 객체는 자신이 호출하지 않는 메서드에 의존하지 않아야 한다.
- 하나의 인터페이스에 공통되지 않는 메서드를 선언해 구현하는 경우 위배
- 공통되지 않는 인터에피스는 분리해서 따로 선언한다.

## 의존성 역전의 원칙 Dependency Inversion Principle (DIP)

- 객체는 저수준 모듈보다 고수준 모듈에 의존해야한다.
  - 저수준 모듈 : 구현된 객체
  - 고수준 모듈 : 추상 객체
