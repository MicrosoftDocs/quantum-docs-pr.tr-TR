---
title: Q#Standart kitaplıklardaki matematik
description: Q#Yerleşik veri türleriyle kullanılan standart kitaplıkların klasik matematik işlevleri hakkında bilgi edinin.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a3747eaa2c91e482ded3af1279a0e40d922bfb3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868432"
---
# <a name="classical-mathematical-functions"></a>Klasik matematik Işlevleri #

Bu işlevler öncelikle, Q# ve yerleşik veri türleriyle çalışmak için kullanılır `Int` `Double` `Range` .

<xref:microsoft.quantum.intrinsic.random>İşlem imzaya sahip `(Double[] => Int)` .
Giriş olarak Double bir dizisini alır ve dizi içine rastgele seçili bir dizin döndürür `Int` .
Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır. sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.
Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.
