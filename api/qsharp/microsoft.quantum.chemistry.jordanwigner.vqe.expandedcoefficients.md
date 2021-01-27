---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: Expandedkatsayıları işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835615"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="eeb05-102">Expandedkatsayıları işlevi</span><span class="sxs-lookup"><span data-stu-id="eeb05-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="eeb05-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="eeb05-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="eeb05-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="eeb05-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="eeb05-105">Bu ve Pauli terimleri arasında bire bir eşleme elde etmek için Jordan-Wigner katsayısının Compact gösterimini genişletir.</span><span class="sxs-lookup"><span data-stu-id="eeb05-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="eeb05-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="eeb05-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="eeb05-107">Coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="eeb05-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="eeb05-108">Jordan-Wigner Hamiltonian veri yapısından okunan bir dizi katsayısıdır.</span><span class="sxs-lookup"><span data-stu-id="eeb05-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="eeb05-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eeb05-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eeb05-110">Jordan-Wigner teriminin türü.</span><span class="sxs-lookup"><span data-stu-id="eeb05-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="eeb05-111">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="eeb05-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="eeb05-112">Her Pauli dönemi için bir adet genişletilmiş katsayıların dizileri.</span><span class="sxs-lookup"><span data-stu-id="eeb05-112">Expanded arrays of coefficients, one per Pauli term.</span></span>