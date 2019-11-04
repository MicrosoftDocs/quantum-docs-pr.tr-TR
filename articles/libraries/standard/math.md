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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="f5b15-103">Klasik matematik Işlevleri</span><span class="sxs-lookup"><span data-stu-id="f5b15-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="f5b15-104">Bu işlevler öncelikle `Int`, `Double`ve `Range`Q # yerleşik veri türleriyle çalışmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="f5b15-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="f5b15-105"><xref:microsoft.quantum.intrinsic.random> işleminde imza `(Double[] => Int)`vardır.</span><span class="sxs-lookup"><span data-stu-id="f5b15-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="f5b15-106">Giriş olarak Double bir dizisini alır ve bir `Int`olarak diziye rastgele seçilmiş bir dizin döndürür.</span><span class="sxs-lookup"><span data-stu-id="f5b15-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="f5b15-107">Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır.</span><span class="sxs-lookup"><span data-stu-id="f5b15-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="f5b15-108">sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.</span><span class="sxs-lookup"><span data-stu-id="f5b15-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="f5b15-109">Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="f5b15-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>