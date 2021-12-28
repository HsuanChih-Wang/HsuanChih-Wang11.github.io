---
layout: post
title: 巨觀車流理論-流量守恆方程式推導
categories: traffic-theories
description: 由時間和空間維度推導巨觀車流公式
keywords: macroscopic traffic flow
mathjax: true
---

在巨觀車流理論中，流量守恆方程式（Conservation Equation）表示為下：

$$
\frac{∂q(x,t)}{∂x} + \frac{∂k(x,t)}{∂t}= 0
$$

流量（q）和密度（k）皆可表示為空間距離（x）和時間（t）的函數。
但這個公式是怎麼來的呢？ 乍看之下蠻不直覺的，以下推導流量守恆方程式：

<img src="/images/posts/traffic/microscopic-traffic-fig1.png" width="80%" alt="space-time-diagram"/>

首先畫出一張時空圖。橫軸是時間，縱軸是距離，曲線是每輛車的移動軌跡。

根據定義：
令N為通過車輛數。
流量（q）＝ 通過車輛數 / 單位時間
密度（k）＝ 通過車輛數 / 單位距離

從時空圖我們知道：

$$
N_1= q_{BD}∙∆T\\
N_4= k_{AB}∙∆X\\
N_2= k_{CD}∙∆X\\
N_3= q_{AC}∙∆T\\
$$

我們假設這個路段（藍色框起來範圍）無其他路口分支，也就是說，在這個路段內不會有其他車輛流進或流出，流進範圍內的車輛＝流出範圍內的車輛。
依照流量守恆：

$$
N_1 + N_2 = N_3 + N_4 \\
$$

因此: 

$$
q_{BD}∙∆T+ k_{AB}∙∆X= k_{CD}∙∆X+ q_{AC}∙∆T \\
$$

移項後，我們可以得到：

$$
(q_{BD}-q_{AC})∙∆T+(k_{AB}-k_{CD})∙∆X= 0\\
$$

令: 

$$
∆q = q_{BD}-q_{AC} \\ ∆k=k_{AB}-k_{CD}\\
$$

可推導得：

$$
∆q∙∆T + ∆k∙∆X=0\\
$$

同除 ∆T∙∆X：

$$
\frac{∆q∙∆T}{∆T∙∆X} + \frac{∆k∙∆X}{∆T∙∆X}=0 \\
\frac{∆q}{∆X} + \frac{∆k}{∆T}=0\\
$$

因此推展可得流量守恆方程式（Conservation Equation）：

$$
\frac{∂q(x,t)}{∂x}+\frac{∂k(x,t)}{∂t} = 0\\
$$
