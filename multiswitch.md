

```js
let data = {
  x1: "one",
  x2: "two",
};

function checkData(props) {
  const { x1, x2 } = props;
  switch ((x1, x2)) {
    case ("one", "two"):
      console.log(true);
      break;
    default:
      console.log(false);
  }
}

checkData(data)
```

```bash
true
```


```js
let data = {
  x1: "one",
  x2: "two",
};

function checkData(props) {
  const { x1, x2 } = props;
  switch ((x1, x2)) {
    case ("one", "ttwo"):
      console.log(true);
      break;
    default:
      console.log(false);
  }
}

checkData(data)
```

```bash
false
```
