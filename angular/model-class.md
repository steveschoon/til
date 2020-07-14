# Model Class

Here's a simple person model:

```
export class Person {
  public firstName: string;
  public lastName: string;

  constructor(firstName: string, lastName: string) {
    this.firstName = firstName;
    this.lastName = lastName;
  }
}
```

But TypeScript has a shortcut that saves a lot of keystrokes:

```
export class Person {
  constructor(
    public firstName: string, 
    public lastName: string) {
  }
}
```

