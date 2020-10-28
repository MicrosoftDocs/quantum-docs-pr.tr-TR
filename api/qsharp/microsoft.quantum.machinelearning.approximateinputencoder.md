---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: Yaklaşık Teınputencoder işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 67ef7a47a2e036f0953d946b4ace0e6673b173bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731127"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="7fe72-102">Yaklaşık Teınputencoder işlevi</span><span class="sxs-lookup"><span data-stu-id="7fe72-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="7fe72-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7fe72-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7fe72-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7fe72-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7fe72-105">Bir katsayı ve tolerans kümesi verildiğinde, her katsayısını, belirtilen toleranstan kadar bir hesaplama tabanlı durumu olarak hazırlayan bir durum hazırlama işlemi döndürür.</span><span class="sxs-lookup"><span data-stu-id="7fe72-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="7fe72-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7fe72-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="7fe72-107">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7fe72-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7fe72-108">Verilen katsayılarını bir giriş durumuna kodlarken kullanılacak yaklaşık tolerans.</span><span class="sxs-lookup"><span data-stu-id="7fe72-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="7fe72-109">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7fe72-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7fe72-110">Bir giriş durumuna kodlanacak katsayılar.</span><span class="sxs-lookup"><span data-stu-id="7fe72-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="7fe72-111">Çıkış: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="7fe72-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="7fe72-112">Verilen katsayılarını belirli bir kayıttaki giriş durumu olarak hazırlayan bir durum hazırlama işlemi.</span><span class="sxs-lookup"><span data-stu-id="7fe72-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>