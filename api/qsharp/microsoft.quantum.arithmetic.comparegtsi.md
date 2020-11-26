---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: a0e8ef66f1e1a62d4f6a78364135376810507534
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223502"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="6a0f6-102">CompareGTSI işlemi</span><span class="sxs-lookup"><span data-stu-id="6a0f6-102">CompareGTSI operation</span></span>

<span data-ttu-id="6a0f6-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6a0f6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6a0f6-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="6a0f6-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="6a0f6-105">İmzalanan tamsayı karşılaştırması için sarmalayıcı: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="6a0f6-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6a0f6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6a0f6-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="6a0f6-107">xs: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6a0f6-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="6a0f6-108">İlk $n $-bit numarası</span><span class="sxs-lookup"><span data-stu-id="6a0f6-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="6a0f6-109">YS: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6a0f6-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="6a0f6-110">İkinci $n $-bit numarası</span><span class="sxs-lookup"><span data-stu-id="6a0f6-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="6a0f6-111">Sonuç: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6a0f6-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6a0f6-112">$Xs > YS $ olarak çevrilmiş</span><span class="sxs-lookup"><span data-stu-id="6a0f6-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a0f6-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a0f6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

