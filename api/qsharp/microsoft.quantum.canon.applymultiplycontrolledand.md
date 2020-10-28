---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729467"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="d0f26-102">ApplyMultiplyControlledAnd işlemi</span><span class="sxs-lookup"><span data-stu-id="d0f26-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="d0f26-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d0f26-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d0f26-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0f26-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0f26-105">, Hedef qubitin 0 olarak başlatıldığını varsayarak, birden çok kontrollü bir Toffoli kapısı uygular.</span><span class="sxs-lookup"><span data-stu-id="d0f26-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="d0f26-106">Adjoint işlemi, hedef qubitin 0 olarak sıfırlanacağı varsayılır.</span><span class="sxs-lookup"><span data-stu-id="d0f26-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d0f26-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="d0f26-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="d0f26-108">denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d0f26-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d0f26-109">Denetim qubits</span><span class="sxs-lookup"><span data-stu-id="d0f26-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d0f26-110">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d0f26-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d0f26-111">Hedef qubit</span><span class="sxs-lookup"><span data-stu-id="d0f26-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0f26-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0f26-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

