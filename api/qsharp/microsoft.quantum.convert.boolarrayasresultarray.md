---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 50a2bdb4a73ef9d67d3f5532493c142bb7f753cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727596"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="a652c-102">BoolArrayAsResultArray işlevi</span><span class="sxs-lookup"><span data-stu-id="a652c-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="a652c-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="a652c-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="a652c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a652c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a652c-105">Bir `Bool[]` türü `Result[]` türüne dönüştürür; burada `true` eşlenir ve ile `One` `false` eşlenir `Zero` .</span><span class="sxs-lookup"><span data-stu-id="a652c-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="a652c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a652c-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="a652c-107">Giriş: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a652c-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a652c-108">`Bool[]` dönüştürülecek.</span><span class="sxs-lookup"><span data-stu-id="a652c-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="a652c-109">Çıkış: __geçersiz <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="a652c-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="a652c-110">Öğesini `Result[]` temsil eden `input` .</span><span class="sxs-lookup"><span data-stu-id="a652c-110">A `Result[]` representing the `input`.</span></span>