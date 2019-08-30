# Create Lambda Function

Create `src` folder and switch to it.

```bash
$ cd $LAMBDADIR
$ mkdir src
$ cd src

```

Create `index.ts` under `src` folder and paste the code below into the `index.ts` file.

```typescript
export const handler = async (event: any = {}, content: any = {}): Promise<any> => {
  console.log('value1 =', event.key1);
  console.log('value2 =', event.key2);
  console.log('value3 =', event.key3);
  console.log(process.env.Stage);
  const response = JSON.stringify(event, null, 2);
  return response;
}
```

Create `event.json` for testing.

```json
{
  "key1": "value1",
  "key2": "value2",
  "key3": "value3"
}
```