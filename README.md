# coding_assistant
VueCLI SFC practice app.

[![Netlify Status](https://api.netlify.com/api/v1/badges/8739d799-d12a-4694-96c2-3fb05e1fef8f/deploy-status)](https://app.netlify.com/sites/coding-assistant/deploys)
![GitHub repo size](https://img.shields.io/github/repo-size/ken7253/coding_assistant)

## 概要
Vue CLIの勉強のために制作したデモページです。  

### 使用している技術など
- Vue CLI SFC
- Scss
- Netlify

### 基数変換
10進数をよく使用する各基数に変換します。
単純に`.toString(n)`で10進数を他の基数に変えて返しているだけです。

### カラーコード変換
カラーコードを入力するとRGB値を返します。  
入力は通常の6桁ならそのまま処理し、#ありor3桁の短縮表記なら一度#なしの6桁表記に内部的に変換後処理を行います。  
それ以外の場合はConsoleにエラーを返します。  

### JSON生成
入力フォームに入力された値を整形してJSON形式でダウンロード出来ます。  
ダウンロード処理に関しては `blob` の使用でフロント側で完結しています。  
オプション項目では出力されるJSONのBOMの有無（デフォルトではBOMなし）や出力ファイル名などを指定出来ます。  
現在はvalueの値は文字列だけのサポートですが真偽値や数値・オブジェクトも選択できるようにする予定です。

---

## Command
```
npm install         // Project setup
npm run serve       // Compiles and hot-reloads for development
npm run build       // Compiles and minifies for production
npm run lint        // Lints and fixes files
```

## Customize configuration  
See [Configuration Reference](https://cli.vuejs.org/config/).
