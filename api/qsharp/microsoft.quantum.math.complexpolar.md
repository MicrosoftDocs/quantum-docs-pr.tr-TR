---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Karmaşıkkutupsal Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847342"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="59d7a-102">Karmaşıkkutupsal Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="59d7a-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="59d7a-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="59d7a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="59d7a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59d7a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59d7a-105">Kutupsal biçimdeki karmaşık bir sayıyı temsil eder.</span><span class="sxs-lookup"><span data-stu-id="59d7a-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="59d7a-106">Karmaşık bir sayının kutupsal gösterimi $c = r e ^ {ı t} $.</span><span class="sxs-lookup"><span data-stu-id="59d7a-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="59d7a-107">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="59d7a-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="59d7a-108">Büyüklük: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="59d7a-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="59d7a-109">Mutlak değer $r \ge $0 $c $.</span><span class="sxs-lookup"><span data-stu-id="59d7a-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="59d7a-110">Bağımsız değişken: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="59d7a-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="59d7a-111">$C $ öğesinin \mathbb R $ aşaması $t.</span><span class="sxs-lookup"><span data-stu-id="59d7a-111">The phase $t \in \mathbb R$ of $c$.</span></span>