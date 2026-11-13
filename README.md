# COM INTRO サイトテンプレート(静的サイト)

`<プレフィックス>.com-intro.com` で公開する静的サイトのひな形です。

## はじめかた

1. このページの **「Use this template」** で、自分のリポジトリを作ります。
2. portal(https://portal.com-intro.com/dev/)で **サイトを作成** します。表示される **セットアップコード** は一度しか表示されません。
3. 作ったリポジトリをクローンしたフォルダで、次を実行してコードを貼り付けます。
   ```
   npx comintro init
   ```
   (`gh` を使えない場合は、portal のサイト詳細にある「手動セットアップ」の手順に従ってください。)
4. 次を実行して push すると、約 1〜2 分で公開されます。
   ```
   git commit && git push
   ```

`.github/workflows/comintro.yml` は、サイトの情報が決まってから `npx comintro init` が作るため、このテンプレートには含まれていません。

## 構成

- `site/index.html` — 公開されるページ。お問い合わせフォームの例つき(`my-site` の部分を自分のプレフィックスに置き換えます)。
- ビルド手順が必要な場合(Vite、Astro など)は `package.json` を追加し、`npm run build` の出力を `dist/` に作ります。`package.json` があるとき、workflow は `dist/` を公開します。別のフォルダにする場合は workflow の `COMINTRO_DIR` を指定します(`.` は指定できません)。`package.json` を追加したら、`package-lock.json` も必ずコミットしてください(workflow は `npm ci` を使います)。

詳しい説明: https://portal.com-intro.com/dev/docs/
