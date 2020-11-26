---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: 17a757278500833bc5a5d0635af020cfe1fd569f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218402"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="dec22-102">ApplyMultiplyControlledAnd işlemi</span><span class="sxs-lookup"><span data-stu-id="dec22-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="dec22-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dec22-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dec22-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dec22-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dec22-105">, Hedef qubitin 0 olarak başlatıldığını varsayarak, birden çok kontrollü bir Toffoli kapısı uygular.</span><span class="sxs-lookup"><span data-stu-id="dec22-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="dec22-106">Adjoint işlemi, hedef qubitin 0 olarak sıfırlanacağı varsayılır.</span><span class="sxs-lookup"><span data-stu-id="dec22-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="dec22-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="dec22-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="dec22-108">denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dec22-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dec22-109">Denetim qubits</span><span class="sxs-lookup"><span data-stu-id="dec22-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="dec22-110">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dec22-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dec22-111">Hedef qubit</span><span class="sxs-lookup"><span data-stu-id="dec22-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="dec22-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dec22-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

