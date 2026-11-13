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

中国語ドキュメント: https://portal.com-intro.com/dev/docs/zh/

---

## 中文

# COM INTRO 站点模板(静态站点)

用于发布到 `<前缀>.com-intro.com` 的静态站点模板。

### 开始使用

1. 在本页点击 **「Use this template」**,创建你自己的仓库。
2. 在 portal(https://portal.com-intro.com/dev/)**创建站点**。显示的**设置码**只会出现一次。
3. 在克隆下来的仓库文件夹中执行下面的命令并粘贴设置码(提示信息可用 `COMINTRO_LANG=zh` 切换为中文)。
   ```
   npx comintro init
   ```
   (如果无法使用 `gh`,请按 portal 站点详情中的「手动设置」步骤操作。)
4. 执行下面的命令并 push,约 1~2 分钟后即可公开。
   ```
   git commit && git push
   ```

`.github/workflows/comintro.yml` 要在站点信息确定后由 `npx comintro init` 生成,因此本模板中不包含。

### 结构

- `site/index.html` — 公开的页面。附带联系表单示例(把 `my-site` 替换为你自己的前缀)。
- 如果需要构建步骤(Vite、Astro 等),请添加 `package.json`,并把 `npm run build` 的输出放到 `dist/`。存在 `package.json` 时,workflow 会发布 `dist/`。若要使用其他文件夹,请在 workflow 中指定 `COMINTRO_DIR`(不能指定 `.`)。添加 `package.json` 后,务必同时提交 `package-lock.json`(workflow 使用 `npm ci`)。

详细说明: https://portal.com-intro.com/dev/docs/zh/
