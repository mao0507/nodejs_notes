node.js
===

### init 

1. 開始初始化 node
```shell
$ npm init 
```
- 過程中會出現要填寫的項目

```shell
package name: (9527server) 9527server // 專案名稱
version: (1.0.0) 0.0.1 // 版本號
description:  demo for localhost server // 簡介
entry point: (index.js) index.js // 初始點 
test command: // 測試命令
git repository: // git 位置
keywords:
author: mao  // 作者
license: (ISC) // 授權
About to write to C:\Users\User\Desktop\9527Server\package.json:

{
  "name": "9527server",
  "version": "0.0.1",
  "description": "localhost server ",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "mao",
  "license": "ISC",
}

Is this ok? (yes) yes
```

2. 安裝 TypeScript

```shell
$ npm install --save-dev typescript @types/express @types/node
$ npm install --save express
```

3. 初始化 TypeScript

```
tsc --init
```

- 如果出現
> 無法辨識 'tsc' 詞彙是否為 Cmdlet、函數、指令檔或可執行程式的名稱。請檢查名稱拼字是否正確，如果包含路徑的話，請確認路徑是否正確，然後再試一次。

- 需要全域安裝 typeScript

```shell
npm i -g typescript 
```

- 檢查typescript 是否安裝
```
tsc -v
```


```json
// tsconfig.json
{
  "compilerOptions": {
    "target": "es2016", // 選擇要編譯成哪種版本的 JavaScript
    "module": "commonjs",
    "strict": true, // 嚴格模式，啟用後需要指定函數參數的 type
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "outDir": "dist" // 將編譯過後的js檔放到dist資料夾中
  }
}
```

[tsconfig.json說明](https://www.typescriptlang.org/tsconfig#exclude)

4. 安裝 nodemon 與 ts-node
```shell
$ npm install --save-dev nodemon ts-node
```

5. . 修改 package.json

```json
"scripts": {
  "serve": "nodemon src/app.ts", // 選擇進入點檔案
  "build": "tsc --project ./",
  "test": "echo \"Error: no test specified\" && exit 1"
}
```

### 使用套件

1. yarn 
```shell
$ npm i yarn 
```
2. nodemon 
```shell
$ npm i -g nodemon
```
3. http
```shell
$ npm i http --save
```
4. request
```shell
$ npm i request --save
```
5. typescript
```shell
$ npm i --save-dev typescript @types/express @types/node
$ npm i --save express
```
6. ts-node
```shell
$ npm i ts-node
```
7. body-parser
```shell
$ npm i body-parser
```



### package.json 設定

```json
{
  "name": "9527server",
  "version": "0.0.1",
  "description": "localhost server ",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "serve": "nodemon src/index.ts",
    "build": "tsc --project ./"
  },
  "author": "mao",
  "license": "ISC",
  "devDependencies": {
    "@types/express": "^4.17.17",
    "@types/node": "^18.15.3",
    "typescript": "^5.0.2"
  },
  "dependencies": {
    "body-parser": "^1.20.2",
    "express": "^4.18.2",
    "nodemon": "^2.0.21",
    "ts-node": "^10.9.1",
    "yarn": "^1.22.19"
  }
}



```

### 參考
[【 Node.js 】如何在 Node.js 中建立 TypeScript 的環境](https://jimmyswebnote.com/create-nodejs-project-with-typescript/)

[[Day-1] Node.js 入門[安裝與Hello world]](https://ithelp.ithome.com.tw/articles/10233446)

[用node.js建立一個RESTful API (get/ post)](https://ch543ch543.medium.com/%E7%94%A8node-js%E5%BB%BA%E7%AB%8B%E4%B8%80%E5%80%8Brestful-api-get-post-663e8f80e3fe)