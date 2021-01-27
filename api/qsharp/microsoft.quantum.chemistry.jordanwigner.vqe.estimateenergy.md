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
# <a name="estimateenergy-operation"></a>Estimateenerji işlemi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Bireysel Jordan-Wigner koşullarına göre katkıda bulunulan enerji miktarını toplayarak moleule 'in enerji düzeyini tahmin eder.

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a>Description

Bu işlem dolaylı olarak açılan dizin oluşturma kuralına dayanır.

## <a name="input"></a>Giriş

### <a name="jwhamiltonian--jordanwignerencodingdata"></a>jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Jordan-Wigner Hamiltonian.


### <a name="nsamples--int"></a>nSamples: [Int](xref:microsoft.quantum.lang-ref.int)

Vadeli beklentilerini tahmin etmek için kullanılacak örneklerin sayısı.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

Moleule için tahmini enerji