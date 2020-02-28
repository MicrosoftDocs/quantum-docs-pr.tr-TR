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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="8915f-103">Klasik matematik Işlevleri</span><span class="sxs-lookup"><span data-stu-id="8915f-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="8915f-104">Bu işlevler öncelikle `Int`, `Double`ve `Range`Q # yerleşik veri türleriyle çalışmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="8915f-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="8915f-105"><xref:microsoft.quantum.intrinsic.random> işleminde imza `(Double[] => Int)`vardır.</span><span class="sxs-lookup"><span data-stu-id="8915f-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="8915f-106">Giriş olarak Double bir dizisini alır ve bir `Int`olarak diziye rastgele seçilmiş bir dizin döndürür.</span><span class="sxs-lookup"><span data-stu-id="8915f-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="8915f-107">Belirli bir dizini seçme olasılığı, bu dizindeki dizi öğesinin değeri ile orantılıdır.</span><span class="sxs-lookup"><span data-stu-id="8915f-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="8915f-108">sıfıra eşit olan n dizi öğeleri yok sayılır ve bunların dizinleri hiçbir şekilde döndürülmez.</span><span class="sxs-lookup"><span data-stu-id="8915f-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="8915f-109">Herhangi bir dizi öğesi sıfırdan küçükse veya hiçbir dizi öğesi sıfırdan büyükse, işlem başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="8915f-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
