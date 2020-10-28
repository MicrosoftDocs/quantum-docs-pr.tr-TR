---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Controltadonınt işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728807"
---
# <a name="controlledonint-function"></a><span data-ttu-id="f5778-102">Controltadonınt işlevi</span><span class="sxs-lookup"><span data-stu-id="f5778-102">ControlledOnInt function</span></span>

<span data-ttu-id="f5778-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f5778-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f5778-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5778-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5778-105">Denetim yazmacı durumu belirtilen pozitif tamsayıya karşılık geliyorsa, hedef kayıt üzerinde Oracle uygulayan bir Unitary işleci döndürür.</span><span class="sxs-lookup"><span data-stu-id="f5778-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f5778-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f5778-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="f5778-107">numberState: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5778-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5778-108">Pozitif tamsayı.</span><span class="sxs-lookup"><span data-stu-id="f5778-108">Positive integer.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="f5778-109">Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="f5778-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f5778-110">Unitary işleci.</span><span class="sxs-lookup"><span data-stu-id="f5778-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="f5778-111">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], 't) => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="f5778-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f5778-112">`oracle`Denetim kayıt durumu sayı durumuna karşılık geliyorsa, hedef kayıt üzerinde geçerli olan Unitary işleci `numberState` .</span><span class="sxs-lookup"><span data-stu-id="f5778-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f5778-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f5778-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f5778-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f5778-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="f5778-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f5778-115">Remarks</span></span>

<span data-ttu-id="f5778-116">Değeri, `numberState` küçük endian kodlamalı bir kodlama kullanılarak yorumlanır.</span><span class="sxs-lookup"><span data-stu-id="f5778-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>