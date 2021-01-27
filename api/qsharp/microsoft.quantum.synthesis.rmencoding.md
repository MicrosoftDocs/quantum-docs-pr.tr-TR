---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: Rmenkodlamaya işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: f3c54d2e40511dacb21618b4eaf1eef9f4903f9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855338"
---
# <a name="rmencoding-function"></a><span data-ttu-id="cada8-102">Rmenkodlamaya işlevi</span><span class="sxs-lookup"><span data-stu-id="cada8-102">RMEncoding function</span></span>

<span data-ttu-id="cada8-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="cada8-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="cada8-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cada8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cada8-105">{-1,1} Boolean bir Truth değerinin kodlaması</span><span class="sxs-lookup"><span data-stu-id="cada8-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="cada8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cada8-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="cada8-107">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cada8-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cada8-108">Boole değeri</span><span class="sxs-lookup"><span data-stu-id="cada8-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="cada8-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cada8-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cada8-110">1, `b` yanlışsa, yoksa-1</span><span class="sxs-lookup"><span data-stu-id="cada8-110">1, if `b` is false, otherwise -1</span></span>