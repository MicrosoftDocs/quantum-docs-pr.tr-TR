---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Estimateenerji işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: a64ac3970e3e67568f91b4e67775d834a80c04a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835722"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="e1e18-102">Estimateenerji işlemi</span><span class="sxs-lookup"><span data-stu-id="e1e18-102">EstimateEnergy operation</span></span>

<span data-ttu-id="e1e18-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="e1e18-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="e1e18-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e1e18-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="e1e18-105">Bireysel Jordan-Wigner koşullarına göre katkıda bulunulan enerji miktarını toplayarak moleule 'in enerji düzeyini tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="e1e18-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="e1e18-106">Description</span><span class="sxs-lookup"><span data-stu-id="e1e18-106">Description</span></span>

<span data-ttu-id="e1e18-107">Bu işlem dolaylı olarak açılan dizin oluşturma kuralına dayanır.</span><span class="sxs-lookup"><span data-stu-id="e1e18-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="e1e18-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="e1e18-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="e1e18-109">jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="e1e18-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="e1e18-110">Jordan-Wigner Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="e1e18-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="e1e18-111">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1e18-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1e18-112">Vadeli beklentilerini tahmin etmek için kullanılacak örneklerin sayısı.</span><span class="sxs-lookup"><span data-stu-id="e1e18-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="e1e18-113">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e1e18-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e1e18-114">Moleule için tahmini enerji</span><span class="sxs-lookup"><span data-stu-id="e1e18-114">The estimated energy of the molecule</span></span>