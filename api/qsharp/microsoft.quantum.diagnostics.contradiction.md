---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Çelişme işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829360"
---
# <a name="contradiction-function"></a><span data-ttu-id="e0a1c-102">Çelişme işlevi</span><span class="sxs-lookup"><span data-stu-id="e0a1c-102">Contradiction function</span></span>

<span data-ttu-id="e0a1c-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e0a1c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e0a1c-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e0a1c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e0a1c-105">Klasik koşulun yanlış olduğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="e0a1c-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e0a1c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e0a1c-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="e0a1c-107">gerçek: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e0a1c-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e0a1c-108">Belirtilecek koşul.</span><span class="sxs-lookup"><span data-stu-id="e0a1c-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="e0a1c-109">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e0a1c-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e0a1c-110">Klasik koşulun doğru olması durumunda yazdırılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="e0a1c-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e0a1c-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0a1c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="e0a1c-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="e0a1c-112">Example</span></span>

<span data-ttu-id="e0a1c-113">Aşağıdaki Q # kodu "Merhaba, Dünya" olarak basılacak:</span><span class="sxs-lookup"><span data-stu-id="e0a1c-113">The following Q# code will print "Hello, world":</span></span>

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a><span data-ttu-id="e0a1c-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e0a1c-114">See Also</span></span>

- [<span data-ttu-id="e0a1c-115">Microsoft. hisse. Diagnostics. olgu</span><span class="sxs-lookup"><span data-stu-id="e0a1c-115">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)