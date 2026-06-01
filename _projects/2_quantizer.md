---
layout: page
title: 動的量子化器
description: 離散値入力システムにおける動的量子化器の評価（倒立振子制御）
importance: 2
category: research
---

舞鶴工業高等専門学校での研究です。離散値入力システムにおける**動的量子化器**を設計・評価しました。

MATLAB と ODQ Toolbox を用いて倒立振子の制御を行い、Arduino（8bit マイコン）・エンコーダ・LEGO で実機を構成しました。

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <video class="img-fluid rounded z-depth-1" autoplay loop muted playsinline>
            <source src="{{ '/assets/video/pendulumFHD.mp4' | relative_url }}" type="video/mp4">
        </video>
    </div>
</div>
<div class="caption">
    倒立振子の制御実験。
</div>

参考文献：
- [離散値入力型制御における最適動的量子化器](https://www.jstage.jst.go.jp/article/iscie1988/20/3/20_3_122/_pdf)
- [多目的最適化手法に基づく動的量子化器の設計](https://www.maizuru-ct.ac.jp/wp-content/uploads/2020/02/20191028162045479.pdf)
