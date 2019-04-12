```ts
type Mutable<T> = {
  -readonly[P in keyof T]: T[P]
};

type Immutable<T> = {
  +readonly[P in keyof T]: T[P]
};
```
