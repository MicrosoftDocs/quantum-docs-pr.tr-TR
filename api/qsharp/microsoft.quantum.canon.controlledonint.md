---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Controltadonınt işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 6c7f46c44f2a2427f702e463195f26660cb4fca1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840780"
---
# <a name="controlledonint-function"></a><span data-ttu-id="bfb0b-102">Controltadonınt işlevi</span><span class="sxs-lookup"><span data-stu-id="bfb0b-102">ControlledOnInt function</span></span>

<span data-ttu-id="bfb0b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bfb0b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bfb0b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bfb0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bfb0b-105">Denetim yazmacı durumu belirtilen pozitif tamsayıya karşılık geliyorsa, hedef kayıt üzerinde Oracle uygulayan bir Unitary işleci döndürür.</span><span class="sxs-lookup"><span data-stu-id="bfb0b-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="bfb0b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="bfb0b-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="bfb0b-107">numberState: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bfb0b-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bfb0b-108">Pozitif tamsayı.</span><span class="sxs-lookup"><span data-stu-id="bfb0b-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="bfb0b-109">Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL</span><span class="sxs-lookup"><span data-stu-id="bfb0b-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bfb0b-110">Unitary işleci.</span><span class="sxs-lookup"><span data-stu-id="bfb0b-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="bfb0b-111">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], 't) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="bfb0b-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bfb0b-112">`oracle`Denetim kayıt durumu sayı durumuna karşılık geliyorsa, hedef kayıt üzerinde geçerli olan Unitary işleci `numberState` .</span><span class="sxs-lookup"><span data-stu-id="bfb0b-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bfb0b-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="bfb0b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bfb0b-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="bfb0b-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="bfb0b-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bfb0b-115">Remarks</span></span>

<span data-ttu-id="bfb0b-116">Değeri, `numberState` küçük endian kodlamalı bir kodlama kullanılarak yorumlanır.</span><span class="sxs-lookup"><span data-stu-id="bfb0b-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>