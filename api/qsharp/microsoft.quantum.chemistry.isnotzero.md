---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204071"
---
# <a name="isnotzero-function"></a><span data-ttu-id="8ac83-102">IsNotZero işlevi</span><span class="sxs-lookup"><span data-stu-id="8ac83-102">IsNotZero function</span></span>

<span data-ttu-id="8ac83-103">Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="8ac83-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="8ac83-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="8ac83-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="8ac83-105">Bir `Double` sayının yaklaşık olarak sıfır olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="8ac83-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="8ac83-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8ac83-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="8ac83-107">Sayı: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8ac83-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8ac83-108">Denetlenecek numara</span><span class="sxs-lookup"><span data-stu-id="8ac83-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="8ac83-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8ac83-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8ac83-110">Sıfırdan `number` büyük bir mutlak değere sahipse true değerini döndürür `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="8ac83-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>