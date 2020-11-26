---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Controltadonınt işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207267"
---
# <a name="controlledonint-function"></a><span data-ttu-id="9f45f-102">Controltadonınt işlevi</span><span class="sxs-lookup"><span data-stu-id="9f45f-102">ControlledOnInt function</span></span>

<span data-ttu-id="9f45f-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9f45f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9f45f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f45f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f45f-105">Denetim yazmacı durumu belirtilen pozitif tamsayıya karşılık geliyorsa, hedef kayıt üzerinde Oracle uygulayan bir Unitary işleci döndürür.</span><span class="sxs-lookup"><span data-stu-id="9f45f-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="9f45f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9f45f-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="9f45f-107">numberState: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f45f-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f45f-108">Pozitif tamsayı.</span><span class="sxs-lookup"><span data-stu-id="9f45f-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="9f45f-109">Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL</span><span class="sxs-lookup"><span data-stu-id="9f45f-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9f45f-110">Unitary işleci.</span><span class="sxs-lookup"><span data-stu-id="9f45f-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="9f45f-111">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], 't) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="9f45f-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9f45f-112">`oracle`Denetim kayıt durumu sayı durumuna karşılık geliyorsa, hedef kayıt üzerinde geçerli olan Unitary işleci `numberState` .</span><span class="sxs-lookup"><span data-stu-id="9f45f-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9f45f-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9f45f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9f45f-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="9f45f-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="9f45f-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9f45f-115">Remarks</span></span>

<span data-ttu-id="9f45f-116">Değeri, `numberState` küçük endian kodlamalı bir kodlama kullanılarak yorumlanır.</span><span class="sxs-lookup"><span data-stu-id="9f45f-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>