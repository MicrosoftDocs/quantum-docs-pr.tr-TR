---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: eb4116b60bb415465375e374ad84e990135c231c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206553"
---
# <a name="isresultone-function"></a><span data-ttu-id="f628f-102">IsResultOne işlevi</span><span class="sxs-lookup"><span data-stu-id="f628f-102">IsResultOne function</span></span>

<span data-ttu-id="f628f-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f628f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f628f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f628f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f628f-105">Belirli bir sonuç değerinin değerine eşit olup olmadığını sınar `One` .</span><span class="sxs-lookup"><span data-stu-id="f628f-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="f628f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f628f-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="f628f-107">Giriş: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="f628f-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="f628f-108">`Result` Sınanacak değer.</span><span class="sxs-lookup"><span data-stu-id="f628f-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f628f-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f628f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f628f-110">`true` `input` Şuna eşitse, döndürür `One` .</span><span class="sxs-lookup"><span data-stu-id="f628f-110">Returns `true` if `input` is equal to `One`.</span></span>