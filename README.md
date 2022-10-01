# Steps to reproduce

1. npm install && npm start
2. Edit `src/types.ts` to add a new property in `IObj` like this and **save**:

```typescript
export type IObj = {
  name: string;
  age: number;
  newProp?: number;
};
```
There should not be any error in terminal after saving.

3. Edit `src/index.ts` to add the new property in `obj` like this and **save**:

```typescript
import { IObj } from './type';

let obj: IObj = {
  age: 13,
  name: '123',
  newProp: 1,
};

const _name = obj.name;
```
There should not be any error in terminal after saving.

4. Edit `src/index.tsx` to use the new property like this and **save**:
```typescript
import { IObj } from './type';

let obj: IObj = {
  age: 13,
  name: '123',
  newProp: 1,
};

const _name = obj.name;
const _newProp = obj.newProp;
```
It throws the error:
```typescript
Failed to compile.

[eslint] 
src/index.tsx
  Line 10:7:  Unsafe assignment of an `any` value  @typescript-eslint/no-unsafe-assignment

Search for the keywords to learn more about each error.
ERROR in [eslint] 
src/index.tsx
  Line 10:7:  Unsafe assignment of an `any` value  @typescript-eslint/no-unsafe-assignment

Search for the keywords to learn more about each error.

webpack compiled with 1 error
No issues found.
```

You need to save to re-compile after each step, otherwise it may not reproduce.