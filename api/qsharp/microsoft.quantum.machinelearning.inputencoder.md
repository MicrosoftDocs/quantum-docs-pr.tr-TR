---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: Inputencoder işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 019161c0ef6cdec6875518ab58c8159b0f142149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211755"
---
# <a name="inputencoder-function"></a><span data-ttu-id="94c69-102">Inputencoder işlevi</span><span class="sxs-lookup"><span data-stu-id="94c69-102">InputEncoder function</span></span>

<span data-ttu-id="94c69-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="94c69-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="94c69-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="94c69-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="94c69-105">Bir katsayı kümesi ve tolerans verildiğinde, her katsayısını bir hesaplama tabanlı durumun ilgili gensliği olarak hazırlayan bir durum hazırlama işlemi döndürür.</span><span class="sxs-lookup"><span data-stu-id="94c69-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="94c69-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="94c69-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="94c69-107">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="94c69-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="94c69-108">Bir giriş durumuna kodlanacak katsayılar.</span><span class="sxs-lookup"><span data-stu-id="94c69-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="94c69-109">Çıkış: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="94c69-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="94c69-110">Verilen katsayılarını belirli bir kayıttaki giriş durumu olarak hazırlayan bir durum hazırlama işlemi.</span><span class="sxs-lookup"><span data-stu-id="94c69-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>