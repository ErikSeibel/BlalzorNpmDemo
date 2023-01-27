# BlazorNpmDemo

Du schreibst deinen JavaScript oder TypeScript Code in den [JavaScript/src/](https://github.com/TheSwerik/BlalzorNpmDemo/tree/main/NpmInBlazor.Client/JavaScript/src) Ordner.

Wenn die [Blazor Server `.csproj`](https://github.com/TheSwerik/BlalzorNpmDemo/blob/main/NpmInBlazor.Server/NpmInBlazor.Server.csproj#L9-L13) oder die [Blazor Client `.csproj`](https://github.com/TheSwerik/BlalzorNpmDemo/blob/main/NpmInBlazor.Client/NpmInBlazor.Client.csproj#L15-L19) und die [tsconfig.json](https://github.com/TheSwerik/BlalzorNpmDemo/blob/main/NpmInBlazor.Server/JavaScript/tsconfig.json), [webpack.config.js](https://github.com/TheSwerik/BlalzorNpmDemo/blob/main/NpmInBlazor.Server/JavaScript/webpack.config.js), [package.json](https://github.com/TheSwerik/BlalzorNpmDemo/blob/main/NpmInBlazor.Server/JavaScript/package.json) richtig eingestellt sind, sollte der automatisch beim dotnet run, build, publish, etc. alle JS/TS files in eine große bundle.js in `wwwroot/js/index.bundle.js` schreiben.

Diese kannst du in die [index.html](https://github.com/TheSwerik/BlalzorNpmDemo/blob/main/NpmInBlazor.Client/wwwroot/index.html#L30) oder [_Host.cshtml](https://github.com/TheSwerik/BlalzorNpmDemo/blob/main/NpmInBlazor.Server/Pages/_Host.cshtml#L33) importieren und dann mit [IJsRuntime](https://github.com/TheSwerik/BlalzorNpmDemo/blob/main/NpmInBlazor.Server/Pages/Index.razor#L23) nutzen.

# Reasoning

* Ein eigener JavaScript Ordner, damit die config files, node_modules, etc. nicht das Projekt zumüllen
* Das `[PROJEKT]/wwwroot/js/index.bundle.js` ist im .gitignore, weil die eh bei jedem dotnet Befehl neu generiert wird und deshalb wird das (je nachdem wie viele npm packages man nutzt) einfach eine unnötig große Date im git, die nach jeder Änderung neu gepusht werden muss.
* In production mode braucht man die index.bundle.js.map nicht, und aus code obscurity Gründen will man die wahrscheinlich auch nicht
