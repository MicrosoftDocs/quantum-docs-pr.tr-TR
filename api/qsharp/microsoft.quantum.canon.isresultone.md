---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: fa8845fd92e5c16b4ff15436caf42df4f1e151cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728651"
---
# <a name="isresultone-function"></a><span data-ttu-id="a43a0-102">IsResultOne işlevi</span><span class="sxs-lookup"><span data-stu-id="a43a0-102">IsResultOne function</span></span>

<span data-ttu-id="a43a0-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a43a0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a43a0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a43a0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a43a0-105">Belirli bir sonuç değerinin değerine eşit olup olmadığını sınar `One` .</span><span class="sxs-lookup"><span data-stu-id="a43a0-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="a43a0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a43a0-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="a43a0-107">Giriş: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="a43a0-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="a43a0-108">`Result` Sınanacak değer.</span><span class="sxs-lookup"><span data-stu-id="a43a0-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a43a0-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a43a0-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a43a0-110">`true` `input` Şuna eşitse, döndürür `One` .</span><span class="sxs-lookup"><span data-stu-id="a43a0-110">Returns `true` if `input` is equal to `One`.</span></span>