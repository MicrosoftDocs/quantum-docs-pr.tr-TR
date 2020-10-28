---
title: :::no-loc(Q#):::Standart kitaplıklardaki matematik
description: :::no-loc(Q#):::Yerleşik veri türleriyle kullanılan standart kitaplıkların klasik matematik işlevleri hakkında bilgi edinin.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692065"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="c1e1c-103">Klasik matematik Işlevleri</span><span class="sxs-lookup"><span data-stu-id="c1e1c-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="c1e1c-104">Bu işlevler öncelikle, :::no-loc(Q#)::: ve yerleşik veri türleriyle çalışmak için kullanılır `Int` `Double` `Range` .</span><span class="sxs-lookup"><span data-stu-id="c1e1c-104">These functions are primarily used to work with the :::no-loc(Q#)::: built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="c1e1c-105"><xref:Microsoft.Quantum.Intrinsic.Random>İşlem imzaya sahip `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="c1e1c-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="c1e1c-106">Giriş olarak Double bir dizisini alır ve dizi içine rastgele seçili bir dizin döndürür `Int` .</span><span class="sxs-lookup"><span data-stu-id="c1e1c-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="c1e1c-107">Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="c1e1c-108">sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="c1e1c-109">Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
