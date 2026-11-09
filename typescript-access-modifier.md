## Access Modifiers in TypeScript OOP

Access modifiers are used to control how class members can be accessed and changed. TypeScript supports three visibility modifiers like "public", "private", and "protected". Alongside, a "readonly" modifier is used for restricting reassignment. They all help protect a class's internal state.

A "public" member can be accessed from anywhere and is also the default modifier. 

```typescript
class Account {
  public owner: string;

  constructor(owner: string) {
    this.owner = owner;
  }
}
```

A "private" member can be accessed only inside the declaring class and will run into an error if accessed from outside the class.

```typescript
class Account {
  private balance = 0;

  deposit(amount: number) {
    this.balance += amount;
  }
}
``` 

A "protected" member can be accessed from its declaring class as well as its subclasses but not from anywhere else.

```typescript
class Account {
  protected balance = 0;
}

class BusinessAccount extends Account {
  describe() {
    return this.balance;
  }
}
``` 

A "readonly" will prevent reassignment but will allow read operations. 

```typescript
class Account {
  readonly statement: string;

  constructor(statement: string) {
    this.statement = statement;
  }
}
```

In conclusion, "public" should be used for supported class API and any non-sensitive information, "private" for implementation details, "protected" for shared states, and "readonly" for values that should not be reassigned. These modifiers make class design clean while not hampering their runtime efficiency.