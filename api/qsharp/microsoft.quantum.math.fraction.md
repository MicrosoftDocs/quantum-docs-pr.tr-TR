---
uid: Microsoft.Quantum.Math.Fraction
title: Kesir Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857507"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="f1512-102">Kesir Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="f1512-102">Fraction user defined type</span></span>

<span data-ttu-id="f1512-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f1512-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f1512-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1512-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1512-105">Formun bir Rational numarasını temsil eder `p/q` .</span><span class="sxs-lookup"><span data-stu-id="f1512-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="f1512-106">Tamsayı, `p` kayıt düzeninin ilk öğesidir ve `q` kayıt düzeninin ikinci öğesidir.</span><span class="sxs-lookup"><span data-stu-id="f1512-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="f1512-107">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="f1512-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="f1512-108">Pay: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1512-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1512-109">Kesirin pay değeri.</span><span class="sxs-lookup"><span data-stu-id="f1512-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="f1512-110">Payda: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1512-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1512-111">Kesir paydası/</span><span class="sxs-lookup"><span data-stu-id="f1512-111">Denominator of the fraction/</span></span>