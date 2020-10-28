---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731623"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="ebcf9-102">CompareGTSI işlemi</span><span class="sxs-lookup"><span data-stu-id="ebcf9-102">CompareGTSI operation</span></span>

<span data-ttu-id="ebcf9-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ebcf9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ebcf9-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ebcf9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ebcf9-105">İmzalanan tamsayı karşılaştırması için sarmalayıcı: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="ebcf9-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ebcf9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ebcf9-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="ebcf9-107">xs: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ebcf9-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="ebcf9-108">İlk $n $-bit numarası</span><span class="sxs-lookup"><span data-stu-id="ebcf9-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="ebcf9-109">YS: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ebcf9-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="ebcf9-110">İkinci $n $-bit numarası</span><span class="sxs-lookup"><span data-stu-id="ebcf9-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="ebcf9-111">Sonuç: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ebcf9-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ebcf9-112">$Xs > YS $ olarak çevrilmiş</span><span class="sxs-lookup"><span data-stu-id="ebcf9-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="ebcf9-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ebcf9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

