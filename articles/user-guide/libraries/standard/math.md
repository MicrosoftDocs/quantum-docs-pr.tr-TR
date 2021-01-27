---
title: Q#Standart kitaplıklardaki matematik
description: Q#Yerleşik veri türleriyle kullanılan standart kitaplıkların klasik matematik işlevleri hakkında bilgi edinin.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: a2e2656f42213c8ae9e984f63f3ebf4058520532
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853990"
---
# <a name="classical-mathematical-functions"></a>Klasik matematik Işlevleri #

Bu işlevler öncelikle, Q# ve yerleşik veri türleriyle çalışmak için kullanılır `Int` `Double` `Range` .

<xref:Microsoft.Quantum.Intrinsic.Random>İşlem imzaya sahip `(Double[] => Int)` .
Giriş olarak Double bir dizisini alır ve dizi içine rastgele seçili bir dizin döndürür `Int` .
Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır. sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.
Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.
