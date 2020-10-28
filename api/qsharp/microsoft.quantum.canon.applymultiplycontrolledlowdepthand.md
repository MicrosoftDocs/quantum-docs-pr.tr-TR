---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729462"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="205f8-102">ApplyMultiplyControlledLowDepthAnd işlemi</span><span class="sxs-lookup"><span data-stu-id="205f8-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="205f8-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="205f8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="205f8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="205f8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="205f8-105">, Hedef qubitin 0 olarak başlatıldığını varsayarak, birden çok kontrollü bir Toffoli kapısı uygular.</span><span class="sxs-lookup"><span data-stu-id="205f8-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="205f8-106">Adjoint işlemi, hedef qubitin 0 olarak sıfırlanacağı varsayılır.</span><span class="sxs-lookup"><span data-stu-id="205f8-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="205f8-107">RZ derinliğine sahip olmak için 1, yardımcı qubit sayısı, qubit sayısında üstel olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="205f8-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="205f8-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="205f8-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="205f8-109">denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="205f8-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="205f8-110">Denetim qubits</span><span class="sxs-lookup"><span data-stu-id="205f8-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="205f8-111">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="205f8-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="205f8-112">Hedef qubit</span><span class="sxs-lookup"><span data-stu-id="205f8-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="205f8-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="205f8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

