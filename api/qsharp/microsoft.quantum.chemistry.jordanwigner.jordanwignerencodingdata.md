---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData
title: JordanWignerEncodingData Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerEncodingData
qsharp.summary: Format of data passed from C# to Q# to represent all information for Hamiltonian simulation. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 62988eefa57d8a9e4ed9dcfbdbc6c3b630c6faa2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727793"
---
# <a name="jordanwignerencodingdata-user-defined-type"></a><span data-ttu-id="7a2de-102">JordanWignerEncodingData Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="7a2de-102">JordanWignerEncodingData user defined type</span></span>

<span data-ttu-id="7a2de-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="7a2de-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="7a2de-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a2de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a2de-105">Hamiltonian simülasyonu için tüm bilgileri göstermek üzere C# ' den Q # ' a geçirilen verilerin biçimi.</span><span class="sxs-lookup"><span data-stu-id="7a2de-105">Format of data passed from C# to Q# to represent all information for Hamiltonian simulation.</span></span>
<span data-ttu-id="7a2de-106">Temsil edilen verilerin anlamı onu alan algoritma tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="7a2de-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JordanWignerEncodingData = (Int, Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms, (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), Double);
```

