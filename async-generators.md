```js



function* powers(n) {
  for (let current = n;; current *= n) {
    yield current;
  }
}

// for (let power of powers(3)) {
//   if (power > 50) break;
//   console.log(power);
// }

let powersWithMax = (n, maxValue) => {
    for (let power of powers(n)) {
  if (power > maxValue) break;
  console.log(power);
}
}

let powersWithMaxAsyncNoDifference = async (n, maxValue) => {
    for (let power of powers(n)) {
  if (power > maxValue) break;
  console.log(power);
}
}

powersWithMax(3, 500)
powersWithMaxAsyncNoDifference(3, 500)


async function* powersAsync(n) {
  for (let current = n;; current *= n) {
    yield current;
  }
}

let powersWithMaxAsync = async (n, maxValue) => {
for await (let power of powersAsync(n)) {
  if (power > maxValue) break;
  console.log(power);
}
}

powersWithMaxAsync(3, 500)

// (async function () {
// for await (power of powersAsync(3)) {
//   if (power > 50) break;
//   console.log(power);
// }
// })()



async function* asyncGenerator() {
  var i = 0;
  while (i < 3) {
    yield i++;
  }
}

let get123 = async () => {
  for await (num of asyncGenerator()) {
    console.log(num);
}}


get123()
```
