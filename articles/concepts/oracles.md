---
title: Kuantum oracle’ları
description: İle nasıl çalışacağınızı ve başka bir algoritmaya girdi olarak kullanılan hisse Oracles, kara Box işlemlerini tanımlama hakkında bilgi edinin.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 31e43940fc0607b15ccefcfae6be7122227b3d64
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630310"
---
# <a name="quantum-oracles"></a>Hisse Oracles

Oracle $O $ , başka bir algoritmaya girdi olarak kullanılan "kara kutu" işlemidir.
Genellikle, bu gibi işlemler klasik bir işlev kullanılarak tanımlanır $f: \\ {0, 1 \\ } ^ n \- \\ {0, 1 \\ } ^ d, $ $n $ bit ikili bir giriş alır ve bir $m $ bit ikili çıktı üretir.
Bunu yapmak için, belirli bir ikili girişi $x = (x_ {0 } , X_ {1 } , \noktalar, X_ {n-1 } ) $) göz önünde bulundurun.
Qubit durumları $ \ket { \ VEC{x } } = \ket{X_ {0 } } \otimes \ket{X_ {1 } } \otimes \cnoktalar \otimes \ket{X_ {n-1 } } $ olarak etiketliyoruz.

İlk $ \ket } olarak, {x = \ket{f (x)} $ $O bir $O tanımlamaya çalışır, ancak bu birkaç soruna neden olabilir.
İlk olarak, $f $ farklı bir giriş ve çıkış boyutuna sahip olabilir ($n \ne m $ ), bu nedenle $O uygulamak, $ kayıttaki qubit sayısını değiştirebilir.
İkinci olarak, $n = m olsa bile $ , işlev ters çevrilebilir olmayabilir: bazı $x \ne y için $f (x) = f (y) $ $ , sonra $O \ket {x } = O \ket {y } $, ancak $O ^ \hanger o { \ket x } \ne o ^ \hanger o \ket {y } $.
Bu, ^ \dağılım $O adjoint işlemini oluşturmayamayacağız $ ve Oracles için tanımlanmış bir adjoint 'ın olması anlamına gelir.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Bir Oracle 'ı hesaplama tabanlı durumlar üzerinde etkile tanımlama
Bu sorunlardan her ikisi de $ cevaplarımızı tutmak için $m qubits 'in ikinci bir kaydına bakarak ilgilenebiliriz.
Daha sonra, Oracle 'ın tüm hesaplama tabanlı durumlarında etkisini tanımlayacağız: tüm $x \< \\ 0, 1 \\ } ^ n $ ve $y \in \\ {0, 1 \\ } ^ d $ ,

$ $ \begin{align}
    O (\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f (x)}.
\end{align}
$$

Şimdi, oluşturma ile birlikte $O = O ^ \dağılım $ , bu nedenle daha önceki sorunlardan her ikisi çözümlendik.

> [!TIP]
> Bu $O = O ^ {\dağılım $ olduğunu görmek için } $O, $ tüm $a < \ OPLUS b \oplus b = a $a $ , b \ in \{ 0, 1 \} $.
> Sonuç olarak, \ket{x } \ket{y \oplus f (x)} = \ket{x } \ket{y \oplus f (x) \oplus f (x)} = \ket{x } \ket{y $ $O } .

Bu şekilde, her hesaplama tabanlı durum için Oracle bu şekilde tanımlanması, her bir } } $ durum için $O nasıl davrandığını tanımlar.
Bu, $ tüm hisse işlemleri gibi $O, üzerinde işlem yaptığı durumda doğrusal bir şekilde.
Örneğin, $H \ket{0 } = { \tus+} $ ve $H \ket{1 } = { \tus-} $ tarafından tanımlanan Hadamard işlemini göz önünde bulundurun.
$H $ $ \ket +} $ üzerinde nasıl davranması gerektiğini öğrenmek istiyoruz, { Bu $H, $ Doğrusal olduğunu,

$ $ \begin{align}
H \ket { +} & = \frac{1 } {\sqrt{2 } } H (\ket{0 } + \ket{1 } ) = \frac{1 } {\sqrt{2 } } (h \ket {0 } + H \ket {1 } ) \\ \\ & = \frac{1 } {\sqrt{2 } } (\ket { +} + \ demet { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } -\ket{1 } ) = \ket{0 } .
\end{align}
$$

Oracle $O tanımlama durumunda $ benzer şekilde, { } $n + m qubitleri üzerinde herhangi bir durum $ \ket \ PSI $ $ şöyle yazılabilir.

$ $ \begin{align}
\ket { \ psi } & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \ in \\ {0, 1 \\ } ^ d } \ Alpha (x, y) \ket{x } \ket{y}
\end{align}
$$

Burada $ \Alpha: \\ {0, 1 \\ } ^ n \times \\ {0, 1 \\ } ^ d \ to \mathbb{C } $, $ \tus\psı $ durumunun katsayılarını temsil eder { } . Bu nedenle,

$ $ \begin{align}
O \ket \ { psi } & = O \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \ in \\ {0, 1 \\ } ^ m } \ Alpha (x, y) \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \ in \\ {0, 1 \\ } ^ m } \ Alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \ içinde { \\ 0, 1 \\ } ^ m } \Alpha (x, y) \ket{x } \ket{y \oplus f (x)}.
\end{align}
$$

## <a name="phase-oracles"></a>Phase Oracles
Alternatif olarak, $ $ $O girişine göre bir _aşama_ uygulayarak bir Oracle $O $f kodlayabiliriz $ .
Örneğin, $ $ $ \begin{align gibi $O tanımlayabiliriz}
    O \ket{x } = (-1) ^ {f (x)} \ket{x } .
\end{align}
$ $ Bir evre, başlangıçta hesaplama tabanlı bir durum $ \ket{x $ ile bir yazmaç üzerinde işlem yaptığı takdirde } Bu aşama genel bir aşamadır ve bu nedenle observable değildir.
Ancak bu tür bir Oracle, bir üst konuma veya denetimli bir işleme uygulandığında çok güçlü bir kaynak olabilir.
Örneğin, $ tek bir-qubit işlevi $f _F bir aşamayı veya $O düşünün $ .
Sonra, $ $ \begin{align}
    O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \sı{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} { \tus+}.
\end{align}
$$

Daha genel olarak, Oracles görünümlerinin her ikisi de yalnızca tek bir bit yerine gerçek sayılar döndüren klasik işlevleri temsil edecek şekilde ayarlanabilir.

Oracle 'ı uygulamak için en iyi yolu seçmek, bu Oracle 'ın belirli bir algoritma içinde nasıl kullanılacağına bağlıdır.
Örneğin, [Deutsch-Jozsa algoritması](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) , Oracle 'ın birinci şekilde uygulandığı, [Grover 'in algoritması](https://en.wikipedia.org/wiki/Grover's_algorithm) ikinci şekilde uygulanan Oracle 'ı temel alır.


Daha fazla ayrıntı için [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)' deki tartışmayı öneririz.
