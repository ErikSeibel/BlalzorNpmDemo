# BlalzorNpmDemo

Du schreibst deinen JavaScript oder TypeScript Code in den [NpmInBlazor/JavaScript/src/](https://github.com/TheSwerik/BlalzorNpmDemo/tree/main/NpmInBlazor/JavaScript/src) Ornder.

Wenn die [.csproj](https://github.com/TheSwerik/BlalzorNpmDemo/blob/7fac63646e200c6716ed455988778729cdffa561/NpmInBlazor/NpmInBlazor.csproj#L14-L17) und die [tsconfig.json](https://github.com/TheSwerik/BlalzorNpmDemo/blob/main/NpmInBlazor/JavaScript/tsconfig.json), [webpack.config.js](https://github.com/TheSwerik/BlalzorNpmDemo/blob/main/NpmInBlazor/JavaScript/webpack.config.js), [package.json](https://github.com/TheSwerik/BlalzorNpmDemo/blob/main/NpmInBlazor/JavaScript/package.json) richtig eingestellt sind, dann sollte der automatisch beim dotnet run, build, publish, etc alle JS/TS files in eine bundlen und bereitstellen.
Diese kannst du in die index.html oder index.razor importieren und dann mit IJsRuntime nutzen.
