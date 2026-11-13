# local-assets（手元専用・コミット禁止）

ここには、**再配布が認められていない素材**を置きます。このフォルダの中身は `.gitignore` で除外されており、
GitHub にも GitHub Pages（公開サイト）にも載りません。この README.md だけが共有されます。

## Tinymen - Basic Tiles（RenderHub）

- 配布元：https://www.renderhub.com/juanchee/tinymen-basic-tiles（作者：JuanChee、無料・要ログイン）
- ライセンス：RenderHub の Extended Use License（CC0 ではない）。
  全文：https://www.renderhub.com/info/3d-content-licensing
  素材ファイルの再配布・公開は、作品の一部として組み込む場合を除いて禁止されているため、公開リポジトリには入れない。
- 内容：52点（地面12、水11、坂2、木4種×各3、岩4、茂み4、金鉱3、ベリーの茂み3、崖4）、512×512のテクスチャ1枚。

### 置き方

1. 上の配布ページからダウンロードする（形式は `.glb`。zipのままでよい）。
2. zip を展開し、次の2種類だけを `island/local-assets/tinymen/` に置く。
   - `glb/` の中の `GEO_*.glb`（形だけのモデル。`ARM_*.glb` は使わない）
   - `texture/Overall-Palette_512.png`（**`palette.png` という名前に変えて**置く。この素材の `.glb` には色が入っておらず、このパレット画像のUVで色が決まる）

       island/local-assets/tinymen/GEO_GroundTile.glb ほか
       island/local-assets/tinymen/palette.png

3. 手元で確認する（`file://` では動かないので、簡易サーバーを使う）。

       cd koutaharada59-debug.github.io
       python3 -m http.server 8000
       # ブラウザで http://localhost:8000/island/?tiles=tinymen を開く

`?tiles=tinymen` を付けないとき、またはフォルダに素材がないときは、今までどおりの地形で表示されます（公開サイトはこの状態）。

### コミットの事故を防ぐ確認

    git status --short        # island/local-assets/ の中の素材が出ていないこと
    git check-ignore -v island/local-assets/tinymen/anything.glb   # 無視されていること
