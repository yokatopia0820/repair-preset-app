# Firebase同期設定手順

スマホ、iPad、PCで同じプリセットデータを使うには、Firebase Firestoreを同期先として使います。

## 1. Firebaseプロジェクトを作成

1. Firebase Consoleを開きます。
2. 新しいプロジェクトを作成します。
3. Webアプリを追加します。
4. 表示される `firebaseConfig` をコピーします。

例:

```js
const firebaseConfig = {
  apiKey: "xxxxx",
  authDomain: "xxxxx.firebaseapp.com",
  projectId: "xxxxx",
  storageBucket: "xxxxx.appspot.com",
  messagingSenderId: "xxxxx",
  appId: "xxxxx"
};
```

アプリには `const firebaseConfig =` を除いたJSON部分だけを貼り付けます。

```json
{
  "apiKey": "xxxxx",
  "authDomain": "xxxxx.firebaseapp.com",
  "projectId": "xxxxx",
  "storageBucket": "xxxxx.appspot.com",
  "messagingSenderId": "xxxxx",
  "appId": "xxxxx"
}
```

## 2. Firestore Databaseを有効化

Firebase Consoleで `Firestore Database` を作成します。

まずはテスト用に開始し、業務利用前に必ずアクセス制御を見直してください。

## 3. アプリで同期設定

1. アプリを開きます。
2. `プリセット保存・読込` を押します。
3. `クラウド同期` にFirebase Web設定JSONを貼り付けます。
4. 同期IDを入力します。
5. `同期設定を保存` を押します。

同じFirebase設定と同じ同期IDをスマホ、iPad、PCに入れると、同じプリセットを送受信できます。

## 4. 同期の使い方

- 端末のプリセットをクラウドへ反映する: `クラウドへ送信`
- クラウド上のプリセットを端末へ反映する: `クラウドから読込`

## 注意

Firestoreのセキュリティルールを公開状態にしたまま業務利用しないでください。実運用では、認証や同期ID単位のアクセス制御を設定するのがおすすめです。
