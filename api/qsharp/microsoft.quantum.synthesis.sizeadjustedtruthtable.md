---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Sizeayarlantedtruthtable işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855314"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="2b59e-102">Sizeayarlantedtruthtable işlevi</span><span class="sxs-lookup"><span data-stu-id="2b59e-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="2b59e-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="2b59e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="2b59e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b59e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b59e-105">Değer sayısına göre, bir dizi Boole değerinden Truth tablosunu ayarlar</span><span class="sxs-lookup"><span data-stu-id="2b59e-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="2b59e-106">Yeni bir dizi `2^numVars` , büyük olasılıkla, `table` `false` girdilerle veya öğelere kesilmek için gereken uzunluktadır `2^numVars` .</span><span class="sxs-lookup"><span data-stu-id="2b59e-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="2b59e-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="2b59e-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="2b59e-108">Tablo: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2b59e-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2b59e-109">Gerçeği değeri dizi olarak Truth tablosu</span><span class="sxs-lookup"><span data-stu-id="2b59e-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="2b59e-110">numVars: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b59e-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b59e-111">Değişken sayısı</span><span class="sxs-lookup"><span data-stu-id="2b59e-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="2b59e-112">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2b59e-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2b59e-113">Boyut ayarlanan Truth tablosu</span><span class="sxs-lookup"><span data-stu-id="2b59e-113">Size adjusted truth table</span></span>