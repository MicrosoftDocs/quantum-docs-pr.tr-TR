---
uid: Microsoft.Quantum.Math.Fraction
title: Kesir Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210684"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="313b3-102">Kesir Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="313b3-102">Fraction user defined type</span></span>

<span data-ttu-id="313b3-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="313b3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="313b3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="313b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="313b3-105">Formun bir Rational numarasını temsil eder `p/q` .</span><span class="sxs-lookup"><span data-stu-id="313b3-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="313b3-106">Tamsayı, `p` kayıt düzeninin ilk öğesidir ve `q` kayıt düzeninin ikinci öğesidir.</span><span class="sxs-lookup"><span data-stu-id="313b3-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="313b3-107">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="313b3-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="313b3-108">Pay: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="313b3-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="313b3-109">Kesirin pay değeri.</span><span class="sxs-lookup"><span data-stu-id="313b3-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="313b3-110">Payda: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="313b3-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="313b3-111">Kesir paydası/</span><span class="sxs-lookup"><span data-stu-id="313b3-111">Denominator of the fraction/</span></span>