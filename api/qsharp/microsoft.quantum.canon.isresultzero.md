---
uid: Microsoft.Quantum.Canon.IsResultZero
title: Isresultzero işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: b4e9b62b20e12a8dce544ce16dcddcf15fdf2680
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206536"
---
# <a name="isresultzero-function"></a><span data-ttu-id="515d5-102">Isresultzero işlevi</span><span class="sxs-lookup"><span data-stu-id="515d5-102">IsResultZero function</span></span>

<span data-ttu-id="515d5-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="515d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="515d5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="515d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="515d5-105">Belirli bir sonuç değerinin değerine eşit olup olmadığını sınar `Zero` .</span><span class="sxs-lookup"><span data-stu-id="515d5-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="515d5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="515d5-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="515d5-107">Giriş: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="515d5-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="515d5-108">`Result` Sınanacak değer.</span><span class="sxs-lookup"><span data-stu-id="515d5-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="515d5-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="515d5-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="515d5-110">`true` `input` Şuna eşitse, döndürür `Zero` .</span><span class="sxs-lookup"><span data-stu-id="515d5-110">Returns `true` if `input` is equal to `Zero`.</span></span>