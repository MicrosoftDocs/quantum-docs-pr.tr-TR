---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841668"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="7b2b7-102">ApplyMultiplyControlledLowDepthAnd işlemi</span><span class="sxs-lookup"><span data-stu-id="7b2b7-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="7b2b7-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7b2b7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7b2b7-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b2b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b2b7-105">, Hedef qubitin 0 olarak başlatıldığını varsayarak, birden çok kontrollü bir Toffoli kapısı uygular.</span><span class="sxs-lookup"><span data-stu-id="7b2b7-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="7b2b7-106">Adjoint işlemi, hedef qubitin 0 olarak sıfırlanacağı varsayılır.</span><span class="sxs-lookup"><span data-stu-id="7b2b7-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="7b2b7-107">RZ derinliğine sahip olmak için 1, yardımcı qubit sayısı, qubit sayısında üstel olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="7b2b7-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="7b2b7-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="7b2b7-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="7b2b7-109">denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7b2b7-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7b2b7-110">Denetim qubits</span><span class="sxs-lookup"><span data-stu-id="7b2b7-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7b2b7-111">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7b2b7-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7b2b7-112">Hedef qubit</span><span class="sxs-lookup"><span data-stu-id="7b2b7-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="7b2b7-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b2b7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

