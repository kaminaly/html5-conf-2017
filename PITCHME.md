# 今日からはじめるShader

@kaminaly 安友 裕秋 SHIFTBRAIN Inc.

---

## Shaderって何が出来るの

- グラッフックスの演出(エフェクト)
  - Web
  - Game
  - VJ
- など

---

## メリット

- GPUを使うのでパワフル
- OpenGLが走る環境で使える
  - Three.js Pixi.js
  - oF
  - Processing
  - Unity (別言語があるけどGLSLも使える、OpenGL向けにはGLSLに変換されてる)

---

## 基本

+++

### シェーダにはいくつか種類がある

- バーテックスシェーダ
- ジオメトリシェーダ
- フラグメントシェーダ

+++

### main関数

- バーテックスシェーダ
  - 頂点ごとに実行される
  - 頂点座標を設定する
    - `gl_Position = vec4のデータ;`
    - xy は -1.0 から 1.0 z は 0.0 から 1.0 (wが1.0の時)
- フラグメントシェーダ
  - ピクセルごとに実行される
  - ピクセルの色を設定する
    - `gl_FragColor = vec4のデータ;`
    - rgba は 0.0 から 1.0

+++

### 変数を渡せる

- 渡せる変数にも種類があるけど今回は割愛
- 型も色々あるけど今回は割愛

---

## どうはじめるか

+++

### オンラインエディタではじめる

- メリット
  - テスト環境を自分で用意する必要がない  
    (よく使う変数は、あらかじめ渡されるように設定されている)
  - コードの間違いに気が付きやすい
  - 選択肢がまぁまぁある
- デメリット
  - 欲しい変数がないことがある
  - いざ、自分のプロジェクトに導入しようと思った時に知らなければいけないことが多い

+++

### glslsandbox

http://glslsandbox.com/

- シンプルな構成
- フラグメントシェーダを書ける
- 一番有名かな？

+++

### shadertoy

https://www.shadertoy.com/

- 機能が多い
- フラグメントシェーダをかける
- VR用とかサウンド用にシェーダがかける  
  (そのため`main`関数の名前がちょっと違う)

+++

### Shdr

http://shdr.bkcore.com/

- シンプルな構成
- バーテックスシェーダを書ける
- フラグメントシェーダを書ける

+++

### Kick.js | Shader editor

http://www.kickjs.org/tool/shader_editor/shader_editor.html

- WebGLベースのgameエンジン`KickJS`のShaderエディタ
- 機能が多い
- バーテックスシェーダを書ける
- フラグメントシェーダを書ける

---

## その他ヘルパー

- glslify
  - export/require出来る（コードをモジュール化出来る）
  - `#pragma glslify: export(関数名)`
  - `#pragma glslify: 関数名 = require("./path/to/lib.glsl")`
- glslify-import
  - glslファイルをそのままインポート
  - `#pragma glslify: import("./path/to/lib.glsl")`

---

## 以ーーーーーー上！
