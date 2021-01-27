---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839592"
---
# <a name="isnotzero-function"></a><span data-ttu-id="5e211-102">IsNotZero işlevi</span><span class="sxs-lookup"><span data-stu-id="5e211-102">IsNotZero function</span></span>

<span data-ttu-id="5e211-103">Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5e211-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="5e211-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5e211-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="5e211-105">Bir `Double` sayının yaklaşık olarak sıfır olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="5e211-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="5e211-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5e211-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="5e211-107">Sayı: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e211-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e211-108">Denetlenecek numara</span><span class="sxs-lookup"><span data-stu-id="5e211-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="5e211-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5e211-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5e211-110">Sıfırdan `number` büyük bir mutlak değere sahipse true değerini döndürür `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="5e211-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>