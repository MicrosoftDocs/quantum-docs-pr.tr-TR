---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Sizeayarlantedtruthtable işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734058"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="04981-102">Sizeayarlantedtruthtable işlevi</span><span class="sxs-lookup"><span data-stu-id="04981-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="04981-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="04981-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="04981-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="04981-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="04981-105">Değer sayısına göre, bir dizi Boole değerinden Truth tablosunu ayarlar</span><span class="sxs-lookup"><span data-stu-id="04981-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="04981-106">Yeni bir dizi `2^numVars` , büyük olasılıkla, `table` `false` girdilerle veya öğelere kesilmek için gereken uzunluktadır `2^numVars` .</span><span class="sxs-lookup"><span data-stu-id="04981-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="04981-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="04981-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="04981-108">Tablo: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="04981-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="04981-109">Gerçeği değeri dizi olarak Truth tablosu</span><span class="sxs-lookup"><span data-stu-id="04981-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="04981-110">numVars: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04981-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04981-111">Değişken sayısı</span><span class="sxs-lookup"><span data-stu-id="04981-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="04981-112">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="04981-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="04981-113">Boyut ayarlanan Truth tablosu</span><span class="sxs-lookup"><span data-stu-id="04981-113">Size adjusted truth table</span></span>