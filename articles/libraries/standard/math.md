---
title: 'Q # standart kitaplıkları-matematik | Microsoft Docs'
description: 'Q # standart kitaplıkları-matematik'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184466"
---
# <a name="classical-mathematical-functions"></a>Klasik matematik Işlevleri #

Bu işlevler öncelikle `Int`, `Double`ve `Range`Q # yerleşik veri türleriyle çalışmak için kullanılır.

<xref:microsoft.quantum.intrinsic.random> işleminde imza `(Double[] => Int)`vardır.
Giriş olarak Double bir dizisini alır ve bir `Int`olarak diziye rastgele seçilmiş bir dizin döndürür.
Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır. sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.
Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.