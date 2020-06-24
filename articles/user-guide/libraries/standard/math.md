---
title: 'Q # standart kitaplıklarında matematik'
description: 'Yerleşik veri türleriyle kullanılan Q # standart kitaplıklarında klasik matematik işlevleri hakkında bilgi edinin.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275663"
---
# <a name="classical-mathematical-functions"></a>Klasik matematik Işlevleri #

Bu işlevler öncelikle,, ve ile ilgili olarak Q # yerleşik veri türleriyle çalışmak için `Int` kullanılır `Double` `Range` .

<xref:microsoft.quantum.intrinsic.random>İşlem imzaya sahip `(Double[] => Int)` .
Giriş olarak Double bir dizisini alır ve dizi içine rastgele seçili bir dizin döndürür `Int` .
Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır. sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.
Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.
