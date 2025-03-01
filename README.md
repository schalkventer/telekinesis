_This is still a work in progress, however I've added the initial API documentation_

# 🧙‍♂️ Telekinesis

Create and control web workers directly from JavaScript / Typescript using Promises.

## Basic JS Example

```ts
import { create } from 'telekinesis';

const worker = create(input => input * 2);
worker(10).then(console.log); // 20
```

## Advanced TS Example

```ts
const helpers = {
  triple: (a: number) => a * 3,
  increase: (a: number) => a + 1,
};

const work = create<
  { a: { e: number } },
  { b: { c: number } }
>((x) => {
  return { b: { c: helpers.increase(helpers.triple(x.a.e)) } };
}, helpers);

worker(3).then(console.log); // 10
```
