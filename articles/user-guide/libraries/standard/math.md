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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="82ba9-103">Klasik matematik Işlevleri</span><span class="sxs-lookup"><span data-stu-id="82ba9-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="82ba9-104">Bu işlevler öncelikle,, ve ile ilgili olarak Q # yerleşik veri türleriyle çalışmak için `Int` kullanılır `Double` `Range` .</span><span class="sxs-lookup"><span data-stu-id="82ba9-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="82ba9-105"><xref:microsoft.quantum.intrinsic.random>İşlem imzaya sahip `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="82ba9-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="82ba9-106">Giriş olarak Double bir dizisini alır ve dizi içine rastgele seçili bir dizin döndürür `Int` .</span><span class="sxs-lookup"><span data-stu-id="82ba9-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="82ba9-107">Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır.</span><span class="sxs-lookup"><span data-stu-id="82ba9-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="82ba9-108">sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.</span><span class="sxs-lookup"><span data-stu-id="82ba9-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="82ba9-109">Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="82ba9-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
