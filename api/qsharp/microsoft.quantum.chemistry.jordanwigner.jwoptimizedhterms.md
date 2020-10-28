---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms
title: JWOptimizedHTerms Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JWOptimizedHTerms
qsharp.summary: Format of data passed from C# to Q# to represent terms of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: d75737f23db84f2a21daff7a0ebcb8ae51feb642
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727757"
---
# <a name="jwoptimizedhterms-user-defined-type"></a><span data-ttu-id="b3d2c-102">JWOptimizedHTerms Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="b3d2c-102">JWOptimizedHTerms user defined type</span></span>

<span data-ttu-id="b3d2c-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="b3d2c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="b3d2c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3d2c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3d2c-105">Bmiltonian 'in şartlarını göstermek için C# ' den Q # ' a geçirilen verilerin biçimi.</span><span class="sxs-lookup"><span data-stu-id="b3d2c-105">Format of data passed from C# to Q# to represent terms of the Hamiltonian.</span></span>
<span data-ttu-id="b3d2c-106">Temsil edilen verilerin anlamı onu alan algoritma tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="b3d2c-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JWOptimizedHTerms = (Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[]);
```

