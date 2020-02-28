---
title: 'Q # standart kitaplıklarında matematik'
description: 'Yerleşik veri türleriyle kullanılan Q # standart kitaplıklarında klasik matematik işlevleri hakkında bilgi edinin.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906160"
---
# <a name="classical-mathematical-functions"></a>Klasik matematik Işlevleri #

Bu işlevler öncelikle `Int`, `Double`ve `Range`Q # yerleşik veri türleriyle çalışmak için kullanılır.

<xref:microsoft.quantum.intrinsic.random> işleminde imza `(Double[] => Int)`vardır.
Giriş olarak Double bir dizisini alır ve bir `Int`olarak diziye rastgele seçilmiş bir dizin döndürür.
Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır. sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.
Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.
