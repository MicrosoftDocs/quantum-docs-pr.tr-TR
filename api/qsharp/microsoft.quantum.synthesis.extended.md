---
uid: Microsoft.Quantum.Synthesis.Extended
title: Genişletilmiş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855468"
---
# <a name="extended-function"></a><span data-ttu-id="b6716-102">Genişletilmiş işlev</span><span class="sxs-lookup"><span data-stu-id="b6716-102">Extended function</span></span>

<span data-ttu-id="b6716-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="b6716-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="b6716-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6716-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6716-105">Bir tayfı ters katsayılar ile genişletir</span><span class="sxs-lookup"><span data-stu-id="b6716-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="b6716-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b6716-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="b6716-107">SPIN: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b6716-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b6716-108">Spectral katsayıları</span><span class="sxs-lookup"><span data-stu-id="b6716-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="b6716-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b6716-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b6716-110">Katsayıların ardından ters kopya</span><span class="sxs-lookup"><span data-stu-id="b6716-110">Coefficients followed by inverted copy</span></span>

## <a name="example"></a><span data-ttu-id="b6716-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="b6716-111">Example</span></span>

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```