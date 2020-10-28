---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727373"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="f37c8-102">AllEqualityFactI işlevi</span><span class="sxs-lookup"><span data-stu-id="f37c8-102">AllEqualityFactI function</span></span>

<span data-ttu-id="f37c8-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f37c8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f37c8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f37c8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f37c8-105">İki tamsayı değeri dizilerinin eşit olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="f37c8-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="f37c8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f37c8-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="f37c8-107">gerçek: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f37c8-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f37c8-108">İlgilendiğiniz bir test çalışması tarafından üretilen dizi.</span><span class="sxs-lookup"><span data-stu-id="f37c8-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="f37c8-109">beklenen: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f37c8-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f37c8-110">İlgilendiğiniz test durumundan beklenen dizi.</span><span class="sxs-lookup"><span data-stu-id="f37c8-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="f37c8-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f37c8-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="f37c8-112">Diziler eşit değilse yazdırılacak bir ileti.</span><span class="sxs-lookup"><span data-stu-id="f37c8-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f37c8-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f37c8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

