---
title: Kuantum Sayısal Kitaplığı Tanıtımı | Microsoft Docs
description: Kuantum Sayısal Kitaplığı Tanıtımı
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: 9552f3683e1df8cb10d19d0b3f85223df056f83d
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871357"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>Kuantum Sayısal Kitaplığı Tanıtımı

Birçok kuantum algoritması, matematiksel fonksiyonları girişlerin üst üste konumlandırılmasıyla değerlendiren [oracle](xref:microsoft.quantum.concepts.oracles)’ları kullanır.
Örneğin, Shor’un algoritmasının ana bileşeni, sabit bir $a$ değeri için $f(x) = a^x\operatorname{mod} N$ işlemini, $N$ değerini çarpanlarına ayırmaya yönelik sayıyı ve tüm $2n$-bit dizeleri üzerinde tekdüzen bir bindirme ile $x$ a $2n$-kubit tamsayısını değerlendirir.

Shor’un algoritmasını bir kuantum bilgisayarda çalıştırmak için bu fonksiyonun hedef makinenin yerel işlemlerine göre yazılması gerekir.
$i$-th bit gösterilerek en önemsiz bitten saymaya başlayıp $x$ işleminin ikili gösteriminin $x_i$ ile kullanımı $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$ olarak yazılabilir.
Böylece, bu $a^{2^i x_i}=(a^{2^i})^{x_i}$ işleminin koşullarının ürünü (mod N) olarak yazılabilir. $f(x)$ fonksiyonu, $x_iŞ işleminde koşullu öğe $a^{2^i}$ olacak şekilde $2n$ (modüler) çarpımların dizisi kullanılarak uygulanabilir. $a^{2^i}$ sabitleri önceden hesaplanabilir algoritma çalıştırılmadan önce bundan N sayısı kadar mod azaltılabilir.

Denetimli modüler çarpımların dizisi daha da basitleştirilebilir: Her çarpım, $n$ denetimli modüler toplamalar dizisi kullanılarak gerçekleştirilebilir ve her modüler toplama normal bir toplama işlemi ve karşılaştırıcıdan oluşturulabilir.


Bir uygulamaya ulaşmak için çok fazla adım gerektiğinden bu işlevlere en başta sahip olmak büyük fayda sağlar.
Bu nedenle, Quantum Development Kit geniş bir sayısal işlev yelpazesine yönelik destek sunar.


## <a name="functionality"></a>İşlev

Şu ana kadar bahsedilen tamsayı aritmetiğinin yanı sıra sayısal kitaplık

- Giriş olarak bir veya iki kuantum tamsayının alındığı işaretli (ve işaretsiz) tamsayı işlevi (çarpma, karesini alma, kalanına bölme, evirtim...)
- Giriş olarak bir veya iki kuantum tamsayının alındığı sabit nokta işlevi (ekleme / çıkarma, çarpma, karesini alma, 1/x, polinom değerlendirmesi)

## <a name="getting-started"></a>Başlarken

> [!div class="nextstepaction"]
> [Sayısal kitaplığı kullanma hakkında bilgi edinin](xref:microsoft.quantum.numerics.usage)
