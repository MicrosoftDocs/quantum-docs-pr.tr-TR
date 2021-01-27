---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: Multiplexoperationswithlarregister işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: 91db22d6261709c1c3506c80ff600c904748575a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852471"
---
# <a name="multiplexoperationswithauxregister-operation"></a><span data-ttu-id="35f33-102">Multiplexoperationswithlarregister işlemi</span><span class="sxs-lookup"><span data-stu-id="35f33-102">MultiplexOperationsWithAuxRegister operation</span></span>

<span data-ttu-id="35f33-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="35f33-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="35f33-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35f33-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35f33-105">Çoğullexoperations 'ın uygulama adımı.</span><span class="sxs-lookup"><span data-stu-id="35f33-105">Implementation step of MultiplexOperations.</span></span>

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="35f33-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="35f33-106">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="35f33-107">birimlere göre: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL []</span><span class="sxs-lookup"><span data-stu-id="35f33-107">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>




### <a name="auxillaryregister--qubit"></a><span data-ttu-id="35f33-108">Gııllaryregister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="35f33-108">auxillaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="35f33-109">Dizin: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="35f33-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="35f33-110">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="35f33-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="35f33-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35f33-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="35f33-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="35f33-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35f33-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="35f33-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="35f33-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="35f33-114">See Also</span></span>

- [<span data-ttu-id="35f33-115">Microsoft. hisse. Canon. MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="35f33-115">Microsoft.Quantum.Canon.MultiplexOperations</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperations)