This repo demonstrates a problem with TypeScript.

It's not a problem with the language, it's a problem with the JavaScript code that is generated.

To run

    ts-node index.ts

You get this error:

    > ts-node index.ts
    TypeError: Object prototype may only be an Object or null: undefined
        at setPrototypeOf (native)
        at __extends (C:\projects\github\typescript-circular-class-dependency-problem\lib\dataframe.ts:7:9)
        at C:\projects\github\typescript-circular-class-dependency-problem\lib\dataframe.ts:3:32
        at Object.<anonymous> (C:\projects\github\typescript-circular-class-dependency-problem\lib\dataframe.ts:3:1)
        at Module._compile (module.js:571:32)
        at Module.m._compile (C:\Users\ash\AppData\Roaming\nvm\v7.7.4\node_modules\ts-node\src\index.ts:392:23)
        at Module._extensions..js (module.js:580:10)
        at Object.require.extensions.(anonymous function) [as .ts] (C:\Users\ash\AppData\Roaming\nvm\v7.7.4\node_modules\ts-node\src\index.ts:395:12)
        at Module.load (module.js:488:32)
        at tryModuleLoad (module.js:447:12)


Or build then run

    tsc
    cd build
    node index.js


You get this error:

    > node index.js
    C:\projects\github\typescript-circular-class-dependency-problem\build\lib\dataframe.js:7
            extendStatics(d, b);
            ^

    TypeError: Object prototype may only be an Object or null: undefined
        at setPrototypeOf (native)
        at __extends (C:\projects\github\typescript-circular-class-dependency-problem\build\lib\dataframe.js:7:9)
        at C:\projects\github\typescript-circular-class-dependency-problem\build\lib\dataframe.js:15:5
        at Object.<anonymous> (C:\projects\github\typescript-circular-class-dependency-problem\build\lib\dataframe.js:20:2)
        at Module._compile (module.js:571:32)
        at Object.Module._extensions..js (module.js:580:10)
        at Module.load (module.js:488:32)
        at tryModuleLoad (module.js:447:12)
        at Function.Module._load (module.js:439:3)
        at Module.require (module.js:498:17)