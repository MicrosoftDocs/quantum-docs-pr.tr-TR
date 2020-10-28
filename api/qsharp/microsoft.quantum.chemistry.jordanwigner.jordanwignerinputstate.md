---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 171a2999ab8c73925d4624c565bfd41a4e73c99d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727763"
---
# <a name="jordanwignerinputstate-user-defined-type"></a><span data-ttu-id="41c6b-102">JordanWignerInputState Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="41c6b-102">JordanWignerInputState user defined type</span></span>

<span data-ttu-id="41c6b-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="41c6b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="41c6b-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41c6b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41c6b-105">İlk durumun hazırlanmasını göstermek için C# ' den Q # ' a geçirilen verilerin biçimi, temsil edilen verilerin anlamı onu alan algoritma tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="41c6b-105">Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

