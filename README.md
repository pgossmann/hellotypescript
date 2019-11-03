# hellotypescript
learning basic typescript following instructions https://code.visualstudio.com/docs/typescript/typescript-tutorial

# What I learned with this?
Typescript compiler installed with `npm install typescript -g` globally and with `npm install typescript --save-dev` locally.
Open Visual Studio Code, open a Terminal.
`tsc .\helloworld.ts` will transpile to js file
the js can be run with node `node .\helloworld.js`

added a `tsconfig.json` file

```
{
    "compilerOptions": {
        "target": "es2018",
        "module": "commonjs",
        "sourceMap": true,
        "outDir": "out"
    }
}
```
Now calling `tsc`will transpile everything and put the result in the out folder including sourcemaps.

## Launch F5 debug run
pressing F5, VS Code asks what kind of project, answer `node`. VS Code will create launch.json launch settings in .vscode folder.

```
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "launch",
            "name": "Launch Program",
            "program": "${workspaceFolder}\\helloworld.ts",
            "preLaunchTask": "tsc: build - tsconfig.json",
            "outFiles": [
                "${workspaceFolder}/out/**/*.js"
            ]
        }
    ]
}
```
had to change `"program": "${workspaceFolder}\\helloworld.ts",` to use my ts file.

then set a breakpoint and it stops in the code.


