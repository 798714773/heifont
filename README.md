# heifont
预览字形

使用 https://unpkg.com/vexflow@4.0.0/build/vexflow-debug.js

gen目录生成文本度量
```sh
$ node fontgen_text.js Bravura.otf Bravura_glyphs.ts
``

您可以使用“TextFormatter.registerInfo(...)”注册这些指标，这些指标将可用于您的模块。有关示例，请参见“chordsymbol.ts”。


1生成Gonville字体
要将新的 Gonville 字形添加到 Vexflow，请将字形代码和 SMuFL 名称添加到 `config/valid_codes.json`。然后运行以下命令：
````sh
$ node fontgen_gonville.js ../../src/fonts/
``

2生成 SMuFL 字体
要将新的 SMuFL 字形添加到 Vexflow，请将带有 Gonville 备份代码的 SMuFL 代码添加到`config/valid_codes.json`。然后运行以下命令：
```sh
# 生成 Bravura 字形 生成 Petaluma 字形
$ node fontgen_smufl.js Bravura.otf glyphs_Bravura.ts

# 生成冈维尔字形
$ node fontgen_gonville.js @/gonville/Gonville-18_20200703.otf ../../src/fonts/gonville_glyphs.ts
``

3添加自定义字形
要添加自定义字形，请将其轮廓添加到 `fonts/custom_glyphs.js` 并将自定义代码（带有 `vex` 前缀）添加到 `config/valid_codes.json`。然后运行以下。
```sh
$ node fontgen_gonville.js ../../src/fonts/
``