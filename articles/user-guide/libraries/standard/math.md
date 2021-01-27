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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="549fd-103">Klasik matematik Işlevleri</span><span class="sxs-lookup"><span data-stu-id="549fd-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="549fd-104">Bu işlevler öncelikle, Q# ve yerleşik veri türleriyle çalışmak için kullanılır `Int` `Double` `Range` .</span><span class="sxs-lookup"><span data-stu-id="549fd-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="549fd-105"><xref:Microsoft.Quantum.Intrinsic.Random>İşlem imzaya sahip `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="549fd-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="549fd-106">Giriş olarak Double bir dizisini alır ve dizi içine rastgele seçili bir dizin döndürür `Int` .</span><span class="sxs-lookup"><span data-stu-id="549fd-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="549fd-107">Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır.</span><span class="sxs-lookup"><span data-stu-id="549fd-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="549fd-108">sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.</span><span class="sxs-lookup"><span data-stu-id="549fd-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="549fd-109">Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="549fd-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
