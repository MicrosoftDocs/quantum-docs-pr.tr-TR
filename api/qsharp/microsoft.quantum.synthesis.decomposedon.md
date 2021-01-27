---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855522"
---
# <a name="decomposedon-function"></a>DecomposedOn işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir değişken üzerinde bir permütasyon 'yi kaldırır

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Description

Bir permütasyon $ \pı $ ( `perm` ) ve bir dizin $i $ () verildiğinde `index` , bu yöntem, $ \ pi_l $ ve $ \ pi_r $ görüntülerinin $i $ ve $ \pi ' $ görüntüleri dışındaki dizinlerde bulunan öğelerinde bit değiştirmelerini sağlayan üç permütasyon $ ((\ pi_l, \ pi_r), \pı ') $ döndürür.

## <a name="input"></a>Giriş

### <a name="perm--int"></a>izin: [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>Dizin: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Çıkış: (([Int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])



## <a name="example"></a>Örnek

Girişin izin = [0, 2, 3, 5, 7, 1, 4, 6] ve index = 0 olduğunu varsayalım, bu işlev aşağıdaki tabloya bağlı üç permütasyon hesaplar ve bu durumda, Grup `perm` a 'daki ve Grup D 'deki öğelerle birlikte ikili gösterimde olan permütasyonu listeleyin.  Sütunlarda bit dizinleri listelenir.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

0 ' A eşit olmayan dizinler için tüm değerler (= Dizin), A 'dan B 'ye ve D 'den C 'ye kopyalanır.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

Sonraki bir 0, blok B 'deki 0 sütununda boş bir dizine sahip ilk öğe için konur ve ardından önek eşleşen bir 1 B 'ye yerleştirilir (ilk durumda, 0 0 olan diğer satırda).
Daha sonra, bir 1 blok C içindeki aynı satıra ve blok C içindeki karşılık gelen önek için 0 ' a eklenir.  Bu işlem, tüm dizinler B ve C bloklarına 0 sütununa yerleştirilene kadar yinelenir.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

Tablodan üç yeni permütasyon okuyabiliriz:

- $ \ pi_l $, A içindeki öğeler, B 'deki görüntüler (sol)
- C içindeki öğelerle $ \ pi_r $, C 'deki görüntüler (sağ)
- $ \pi ' $ B 'deki öğelerle, C 'deki görüntüler (geri kalan)

Tasarım bit değerleri, 1 ve 2. dizinler için $ \ pi_l $ ve $ \ pi_r $ içinde değişmez ve 0 dizini için $ \ pi_ ' $ içinde için bit değerleri değişmez.  Ayrıca $ \ pi_l $ ve $ \ pi_r $ öğesinin kendinden ters olması gerektiğini unutmayın.

Türetilmiş ve döndürülen permütasyon: Left = [0, 1, 2, 3, 4, 5, 6, 7] Right = [0, 1, 3, 2, 4, 5, 7, 6] kalanı = [0, 3, 2, 5, 6, 1, 4, 7]