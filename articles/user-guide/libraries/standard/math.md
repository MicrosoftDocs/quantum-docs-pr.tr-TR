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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="b9c4a-103">Klasik matematik Işlevleri</span><span class="sxs-lookup"><span data-stu-id="b9c4a-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="b9c4a-104">Bu işlevler öncelikle, Q# ve yerleşik veri türleriyle çalışmak için kullanılır `Int` `Double` `Range` .</span><span class="sxs-lookup"><span data-stu-id="b9c4a-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="b9c4a-105"><xref:microsoft.quantum.intrinsic.random>İşlem imzaya sahip `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="b9c4a-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="b9c4a-106">Giriş olarak Double bir dizisini alır ve dizi içine rastgele seçili bir dizin döndürür `Int` .</span><span class="sxs-lookup"><span data-stu-id="b9c4a-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="b9c4a-107">Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır.</span><span class="sxs-lookup"><span data-stu-id="b9c4a-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="b9c4a-108">sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.</span><span class="sxs-lookup"><span data-stu-id="b9c4a-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="b9c4a-109">Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="b9c4a-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
