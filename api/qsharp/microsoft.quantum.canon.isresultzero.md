---
uid: Microsoft.Quantum.Canon.IsResultZero
title: Isresultzero işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: 790551690cfba42df4cf7aa77e53e303050bdf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728640"
---
# <a name="isresultzero-function"></a><span data-ttu-id="22f34-102">Isresultzero işlevi</span><span class="sxs-lookup"><span data-stu-id="22f34-102">IsResultZero function</span></span>

<span data-ttu-id="22f34-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="22f34-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="22f34-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22f34-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22f34-105">Belirli bir sonuç değerinin değerine eşit olup olmadığını sınar `Zero` .</span><span class="sxs-lookup"><span data-stu-id="22f34-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="22f34-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="22f34-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="22f34-107">Giriş: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="22f34-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="22f34-108">`Result` Sınanacak değer.</span><span class="sxs-lookup"><span data-stu-id="22f34-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="22f34-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="22f34-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="22f34-110">`true` `input` Şuna eşitse, döndürür `Zero` .</span><span class="sxs-lookup"><span data-stu-id="22f34-110">Returns `true` if `input` is equal to `Zero`.</span></span>