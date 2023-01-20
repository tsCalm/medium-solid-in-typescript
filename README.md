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
