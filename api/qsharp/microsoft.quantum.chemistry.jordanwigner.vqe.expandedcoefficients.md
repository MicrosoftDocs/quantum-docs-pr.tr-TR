---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: Expandedkatsayıları işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 92d7deb7010791e7de3d22ad4616b20110d5e84e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214390"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="dd921-102">Expandedkatsayıları işlevi</span><span class="sxs-lookup"><span data-stu-id="dd921-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="dd921-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="dd921-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="dd921-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="dd921-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="dd921-105">Bu ve Pauli terimleri arasında bire bir eşleme elde etmek için Jordan-Wigner katsayısının Compact gösterimini genişletir.</span><span class="sxs-lookup"><span data-stu-id="dd921-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="dd921-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="dd921-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="dd921-107">Coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dd921-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="dd921-108">Jordan-Wigner Hamiltonian veri yapısından okunan bir dizi katsayısıdır.</span><span class="sxs-lookup"><span data-stu-id="dd921-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="dd921-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd921-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd921-110">Jordan-Wigner teriminin türü.</span><span class="sxs-lookup"><span data-stu-id="dd921-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="dd921-111">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dd921-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="dd921-112">Her Pauli dönemi için bir adet genişletilmiş katsayıların dizileri.</span><span class="sxs-lookup"><span data-stu-id="dd921-112">Expanded arrays of coefficients, one per Pauli term.</span></span>