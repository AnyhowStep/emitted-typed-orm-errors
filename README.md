### The Code

```ts
//test.ts
import * as o from "typed-orm";
o;
```

-----

### Instructions

1. `npm install`
1. `./node_modules/.bin/tsc -v`, should see (`Version 2.9.1`)
1. `npm run check3`

Expected Output : Success after about 17 seconds

Actual Output : Errors after about 37s

-----

The [`typed-orm`](https://github.com/AnyhowStep/typed-orm) project takes about 17s to check,

```
tsc --noEmit --diagnostics

Files:           204
Lines:         61750
Nodes:        327550
Identifiers:  114151
Symbols:      140469
Types:         82340
Memory used: 288116K
I/O read:      0.04s
I/O write:     0.00s
Parse time:    1.23s
Bind time:     0.53s
Check time:   15.91s
Emit time:     0.00s
Total time:   17.67s
```

Transpiling is also fast,

```
tsc -d --diagnostics

Files:           204
Lines:         61750
Nodes:        327550
Identifiers:  114151
Symbols:      140584
Types:         83090
Memory used: 609742K
I/O read:      0.02s
I/O write:     0.09s
Parse time:    1.25s
Bind time:     0.53s
Check time:   16.08s
Emit time:    10.77s
Total time:   28.63s
```

-----

So, while the source code is correct and transpiles, the emitted declarations are riddled with errors.