---
title: Hisse Oracles | Microsoft Docs
description: Hisse Oracles
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 96949b371a3a5a1135d624690933a48ea0214a2e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184721"
---
# <a name="quantum-oracles"></a>Hisse Oracles

Oracle $O $, başka bir algoritmaya girdi olarak kullanılan "kara kutu" işlemidir.
Genellikle, bu gibi işlemler klasik bir işlev kullanılarak tanımlanır $f: \\{0, 1\\} ^ n \ \\{0, 1\\} ^ d $ $n $-bit ikili girişi alan ve bir $m $-bit ikili çıktısı üreten.
Bunu yapmak için belirli bir ikili girişi $x = (X_{0}, X_{1}, \noktalar, X_ {n-1}) $ kullanın.
Qubit durumları $ \ket{\vec{x}} = \ket{X_{0}} \otimes \ket{X_{1}} \otimes \cnoktalar \otimes \ket{X_{n-1}} $ olarak etiketliyoruz.

İlk olarak, \ket{x} = \ket{f (x)} $ $O için $O $ tanımlamalısınız, ancak bu birkaç soruna neden olabilir.
İlk olarak, $f $, kayıttaki qubits sayısını değiştirecek $O şekilde farklı bir giriş ve çıkış boyutuna sahip olabilir ($n \ne m $).
İkinci olarak, $n = m $ olsa bile, işlev ters çevrilebilir olamaz: bazı $x \ne y $ için $f (x) = f (y) $, sonra $O \ket{x} = O\ket {y} $ ancak $O ^ \hanger O\ket {x} \ne O ^ \dağılım O\ket {y} $.
Bu, ^ \dağılım $ $O adjoint işlemini oluşturmayamayacağız ve Oracles için tanımlanmış bir adekin olması gerektiğini gösterir.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Bir Oracle 'ı hesaplama tabanlı durumlar üzerinde etkile tanımlama
Yanıtınızı tutmak için $m $ qubits ikinci bir kaydına bakarak bu sorunlardan her ikisiyle de ilgilenebiliriz.
Ardından, Oracle 'ın tüm hesaplama tabanlı durumlarında etkisini tanımlayacağız: tüm $x \ \\{0, 1\\} ^ n $ ve $y \ \\{0, 1\\} ^ d $,

$ $ \begin{hizalaması} O (\ket{x} \otimes \ket{yı}) = \ket{x} \otimes \ket{y \oplus f (x)}.
\end{hizalaması} $ $

Şimdi $O = O ^ \dağılım $, bu nedenle, daha önceki sorunları çöztik.

> [!TIP]
> Bu $O = O ^ {\abger} $ olduğunu görmek için, $O ^ 2 = \cıvadone $ $a \oplus b \ OPG $ = a $, her $a için, b \ in \{0, 1\}$ olduğunu unutmayın.
> Sonuç olarak, \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{i} $ $O.

Bu şekilde, her hesaplama tabanlı durum $ \ket{x}\ket{y} $ için Oracle bu şekilde tanımlanması, $O $ ' in diğer tüm durumları için nasıl davrandığını da tanımlar.
Bu, tüm hisse işlemleri gibi $O $ ' nin, üzerinde çalıştığı durumda doğrusal olduğunu bulmanızdan hemen sonra takip eder.
Örneğin, $H \demet{0} = \ket{+} $ ve $H \ket{1} = \tus{-}$ tarafından tanımlanan Hadamard işlemini göz önünde bulundurun.
$ \Ket{+} $ üzerinde $H $ ' nin nasıl çalıştığını öğrenmek istiyorsanız, bu $H $ ' nin doğrusal olduğunu,

$ $ \begin{hizalaması} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ayraç{1}) = \frac{1}{\sqrt{2}} (H\demet{0} + H\demet{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ ayraç {+} + \ ayraç{-}) = \frac12 (\demet{0} + \ ayraç{1} + \ ayraç{0}-\ayraç{1}) = \demet{0}.
\end{hizalaması} $ $

Oracle $O $ ' mimizin tanımlanması durumunda benzer bir şekilde $ \ket{\psı} $ $n + m $ qubits olarak yazılabilir

$ $ \begin{hizalaması} \ket{\psı} & = \sum_{x \\\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ ı} \Alpha (x, y) \ket{x} \ket{i} \end{hizalaması} $ $

$ \Alpha: \\{0, 1\\} ^ n \times \\{0, 1\\} ^ d \ to \mathbb{C} $, $ \ket{\psı} $ durumunun katsayılarını temsil eder. Yani

$ $ \begin{hizalaması} O \ket{\psı} & = O \sum_{x \\\{0, 1\\} ^ n, y \ \\{0, 1\\} ^ ı} \Alpha (x, y) \ket{x} \ket{yı} \\\\ & = \sum_{x \\\{0 , 1\\} ^ n, y \ \\{0, 1\\} ^ m} \Alpha (x, y) O \ket{x} \ket{yı} \\\\ & = \sum_{x \In \\{0, 1\\} ^ n, y \ ın \\{0 , 1\\} ^ e} \alfa (x, y) \ket{x} \ket{y \ OPLUS f (x)}.
\end{hizalaması} $ $

## <a name="phase-oracles"></a>Phase Oracles
Alternatif olarak, $O $ girişine göre bir _aşama_ uygulayarak bir Oracle $O $ ' a $f $ ' i kodlayabiliriz.
Örneğin, $ $ \begin{hizalaması} O \ket{x} = (-1) ^ {f (x)} \ket{x} gibi $O $ tanımlayabiliriz.
\end{hizalaması} $ $ bir evre, başlangıçta hesaplama tabanlı bir durum $ \ket{x} $ içinde bir yazmaç üzerinde işlem yaparken, bu aşama genel bir aşamadır ve bu nedenle observable değildir.
Ancak bu tür bir Oracle, bir üst konuma veya denetimli bir işleme uygulandığında çok güçlü bir kaynak olabilir.
Örneğin, $f $ bir tek qubit işlevi için bir Phase Orcale $O _F $ düşünün.
Ardından, $ $ \begin{hizalaması} O_f \ket{+} & = O_f (\demet{0} + \ayraç{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \demet{0} + (-1) ^ {f (1)} \ayraç{1})/\sqrt{2} \\\\ & = (-1) ^ {f ( 0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ayraç{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.
\end{hizalaması} $ $

Daha genel olarak, Oracles görünümlerinin her ikisi de yalnızca tek bir bit yerine gerçek sayılar döndüren klasik işlevleri temsil edecek şekilde ayarlanabilir.

Oracle 'ı uygulamak için en iyi yolu seçmek, bu Oracle 'ın belirli bir algoritma içinde nasıl kullanılacağına bağlıdır.
Örneğin, [Deutsch-Jozsa algoritması](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) , Oracle 'ın birinci şekilde uygulandığı, [Grover 'in algoritması](https://en.wikipedia.org/wiki/Grover's_algorithm) ikinci şekilde uygulanan Oracle 'ı temel alır.


Daha fazla ayrıntı için [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)' deki tartışmayı öneririz.
