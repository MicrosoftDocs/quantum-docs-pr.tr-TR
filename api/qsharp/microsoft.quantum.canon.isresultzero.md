---
uid: Microsoft.Quantum.Canon.IsResultZero
title: Isresultzero işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: b1e7cf6324a2a90f10b6aa93811f2df60fe3afbd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840307"
---
# <a name="isresultzero-function"></a><span data-ttu-id="9c95a-102">Isresultzero işlevi</span><span class="sxs-lookup"><span data-stu-id="9c95a-102">IsResultZero function</span></span>

<span data-ttu-id="9c95a-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9c95a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9c95a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9c95a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9c95a-105">Belirli bir sonuç değerinin değerine eşit olup olmadığını sınar `Zero` .</span><span class="sxs-lookup"><span data-stu-id="9c95a-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="9c95a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9c95a-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="9c95a-107">Giriş: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="9c95a-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="9c95a-108">`Result` Sınanacak değer.</span><span class="sxs-lookup"><span data-stu-id="9c95a-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9c95a-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9c95a-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9c95a-110">`true` `input` Şuna eşitse, döndürür `Zero` .</span><span class="sxs-lookup"><span data-stu-id="9c95a-110">Returns `true` if `input` is equal to `Zero`.</span></span>