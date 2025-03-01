_This is still a work in progress, however I've added the initial API documentation. Will publish on NPM once ready._

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
import { create } from 'telekinesis';

const triple: (a: number) => a * 3;
const increase: (a: number) => a + 1;

const work = create<
  { input: { argument: number } },
  { output: { result: number } }
>((x, helpers) => {
  return { 
    output: { 
      result: helpers.increase(
        helpers.triple(x.input.argument)
      ) 
    }
  };
}, {
  triple,
  increase,
});

worker(3).then(console.log); // { output: { result: 10 } }
```
