# 今日からはじめるShader

@kaminaly 安友 裕秋 SHIFTBRAIN Inc.

---

## Shaderって何が出来るの

- GPU側でプログラムを実行できる |
- グラフィックの演出(エフェクト) |
  - Web |
  - Game |
  - VJ |
  - Media Art |
- CPU負荷の高い演算をやらせる |
- など |

---

## 使う言語

- GLSL (OpenGL) |
- HLSL (DirectX) |
- Cg (OpenGL/DirectX) |
- 今回はGLSLについて話します |

---

## 基本

+++

### シェーダにはいくつか種類がある

- バーテックスシェーダ |
- ジオメトリシェーダ |
- フラグメントシェーダ |
- 今回、ジオメトリシェーダは割愛 |

+++

### バーテックスシェーダ

- 頂点ごとにmain関数が実行される
- 最終的に各頂点座標を設定する


+++

### フラグメントシェーダ

- ピクセルごとにmain関数が実行される
- 最終的に各ピクセルの色を設定する


+++

### 例

+++


### 例 バーテックスシェーダ

```
attribute vec3 position;
uniform mat4 modelViewMatrix;
uniform mat4 projectionMatrix;

void main() {
  //座標変換やら
  vec4 pos = projectionMatrix * modelViewMatrix * vec4(position, 1.0);

  // 座標の設定
  // vec4という型のデータをつかう
  // xy は -1.0 から 1.0 z は 0.0 から 1.0 (wが1.0の時)
  gl_Position = pos;
}
```

+++

### 例 フラグメントシェーダ

```
uniform float time;

void main()
{
  // 色の設定
  // vec4という型のデータをつかう
  // rgba は 0.0 から 1.0
  gl_FragColor = vec4(sin(time) + 1.0);
}
```

+++

### データ型

- void, bool, int, float (見覚えのあるやつ) |
- vec2, vec3, vec4 (座標や色に使えるやつ) |
- mat2, mat3, mat4 (座標変換などに使えるやつ) |
- sampler2D (テクスチャのデータに使うやつ) |

+++

### 変数につくキーワード

- uniform |
  - CPU側のプログラムから渡すやつ |
- attribute |
  - ジオメトリからの情報 |
  - バーテックスシェーダでしか受け取れない |
- varying |
  - vert -> frag に渡すやつ |
  - attributeからのデータを渡したりする |
  - 頂点の座標系からピクセルの座標系に線形補間される |

---

## どうはじめるか

+++

### とにかく、簡単に初めよう
### 楽しむことが一番大事

+++

### オンラインエディタであそぶ

- メリット |
  - テスト環境を自分で用意する必要がない |
  - よく使う変数は、あらかじめ渡されるように設定されている |
  - コードの間違いに気が付きやすい |
  - 選択肢がまぁまぁある |
- デメリット |
  - 欲しい変数がないことがある |
  - いざ、自分のプロジェクトに導入しようと思った時に知らなければいけないことが多い |

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

## 以ーーーーーー上！
