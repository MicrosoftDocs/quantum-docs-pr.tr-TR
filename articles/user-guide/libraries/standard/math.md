---
title: Q#Standart kitaplıklardaki matematik
description: Q#Yerleşik veri türleriyle kullanılan standart kitaplıkların klasik matematik işlevleri hakkında bilgi edinin.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692065"
---
# <a name="classical-mathematical-functions"></a>Klasik matematik Işlevleri #

Bu işlevler öncelikle, Q# ve yerleşik veri türleriyle çalışmak için kullanılır `Int` `Double` `Range` .

<xref:Microsoft.Quantum.Intrinsic.Random>İşlem imzaya sahip `(Double[] => Int)` .
Giriş olarak Double bir dizisini alır ve dizi içine rastgele seçili bir dizin döndürür `Int` .
Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır. sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.
Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.
