# 🧙‍♂️ Telekinesis

Create and control web workers in real-time directly from your JavaScript / Typescript.

```ts
import { create } from 'telekinesis';

const worker = create<number, number>(input => input * 2);
example(10).then(console.log); // 20
```