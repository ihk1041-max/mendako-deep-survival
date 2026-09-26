メンダコ・ディープサバイバル v14 PWA
========================================

このフォルダ一式をHTTPSで公開すると、スマホのホーム画面へ
「アプリ」のように追加して起動できます。

■ 最も簡単な公開方法：GitHub Pages

1. GitHubで新しいRepositoryを作成します。
   例: mendako-game

2. このフォルダ内のファイルをすべてRepositoryのルートへアップロードします。
   index.html
   manifest.webmanifest
   service-worker.js
   icon-192.png
   icon-512.png
   icon-maskable-512.png
   apple-touch-icon.png
   favicon-64.png
   mendako.png

3. GitHubの Repository > Settings > Pages を開きます。

4. Build and deployment で次を指定します。
   Source: Deploy from a branch
   Branch: main
   Folder: / (root)
   → Save

5. 数分待つとURLが表示されます。
   例: https://ユーザー名.github.io/mendako-game/

■ iPhone / iPad

1. 上記URLをSafariで開きます。
2. 共有ボタン（四角＋上矢印）をタップします。
3. 「ホーム画面に追加」を選択します。
4. ホーム画面の「メンダコ」アイコンから起動します。

※ iPhoneではChromeではなくSafariから追加するのが確実です。

■ Android

1. 上記URLをChromeで開きます。
2. ゲーム内の「ホームに追加」、またはChromeメニューを開きます。
3. 「アプリをインストール」または「ホーム画面に追加」を選択します。

■ PWA版の特徴

・ブラウザのアドレスバーがない、アプリ風の独立画面で起動
・一度読み込めばオフラインでも起動可能
・途中保存／「続きから」機能を維持
・ゲーム開始前に「やさしい／ふつう」を選択可能
・やさしい：ライフ5、ダイオウイカの攻撃予告を長く、危険な敵の挟み撃ちを防止
・縦画面／横画面の両方に対応（ゲーム中は横画面推奨）
・BGM、図鑑、実績、永続データを維持
・ホーム画面用の専用メンダコアイコン付き

■ 注意

・index.htmlをfile://で直接開いただけではPWAインストールできません。
  GitHub PagesなどのHTTPS公開が必要です。
・Service Workerの更新は自動で行われますが、更新直後に古い表示が残る場合は
  アプリを一度完全に閉じてから再起動してください。
・iOS/AndroidのOSジェスチャーをWebアプリから完全に禁止することはできません。
  そのため途中状態の自動保存機能は残しています。

■ PCでの簡易確認

このフォルダで以下を実行してください。

  python -m http.server 8000

その後、PCブラウザで http://localhost:8000/ を開きます。
localhostではService Workerをテストできます。
