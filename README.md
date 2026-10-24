# まもるマップ Android版（TWA）

[まもるマップ](https://github.com/ykxlly/mamoru-map)（災害時の公式発表・報道を出典付きで地図に整理するWebアプリ）を、Androidアプリとして配布するためのリポジトリです。

## これは何？

- Web版（`https://mamoru-map-api.krin6525.workers.dev`）を、Trusted Web Activity（TWA）でそのままアプリとして包んでいます。
- アプリ本体の機能はWeb版側にあり、ここにはAndroidのビルド設定だけが入っています。
- [Bubblewrap CLI](https://github.com/GoogleChromeLabs/bubblewrap) で生成しました。

## 主な設定（`twa-manifest.json`）

| 項目 | 値 |
|---|---|
| パッケージ名 | `app.mamorumap.twa` |
| アプリ名 | まもるマップ |
| バージョン | 2（versionName `2`） |
| 起動URL | `/?source=pwa` |

## ビルド方法

```bash
npm install
npx bubblewrap build
```

署名には `./android.keystore`（alias `mamorumap`）を使います。鍵ファイルはGitに含めず、手元で安全に保管してください。

## 状態

Web版をアプリ化するための設定のみ。アプリの機能追加はWeb版（mamoru-map）で行います。
