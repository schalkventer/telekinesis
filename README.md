# 🧙‍♂️ Telekinesis

Create and control web workers directly from JavaScript / Typescript using Promises.

```ts
import { create } from 'telekinesis';

const worker = create(input => input * 2);
worker(10).then(console.log); // 20
```
