---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Estimateenerji işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: fb59071ed05234d4a19cd97598bf479489b9985c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214424"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="8a02f-102">Estimateenerji işlemi</span><span class="sxs-lookup"><span data-stu-id="8a02f-102">EstimateEnergy operation</span></span>

<span data-ttu-id="8a02f-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="8a02f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="8a02f-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="8a02f-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="8a02f-105">Bireysel Jordan-Wigner koşullarına göre katkıda bulunulan enerji miktarını toplayarak moleule 'in enerji düzeyini tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="8a02f-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="8a02f-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="8a02f-106">Description</span></span>

<span data-ttu-id="8a02f-107">Bu işlem dolaylı olarak açılan dizin oluşturma kuralına dayanır.</span><span class="sxs-lookup"><span data-stu-id="8a02f-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="8a02f-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="8a02f-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="8a02f-109">jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="8a02f-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="8a02f-110">Jordan-Wigner Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="8a02f-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="8a02f-111">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8a02f-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8a02f-112">Vadeli beklentilerini tahmin etmek için kullanılacak örneklerin sayısı.</span><span class="sxs-lookup"><span data-stu-id="8a02f-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="8a02f-113">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8a02f-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8a02f-114">Moleule için tahmini enerji</span><span class="sxs-lookup"><span data-stu-id="8a02f-114">The estimated energy of the molecule</span></span>