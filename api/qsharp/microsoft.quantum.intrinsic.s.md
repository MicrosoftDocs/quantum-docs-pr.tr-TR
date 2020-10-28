---
uid: Microsoft.Quantum.Intrinsic.S
title: S işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: 8a57c60ac1df8f6e94b58acf7183c47f395d291a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732447"
---
# <a name="s-operation"></a><span data-ttu-id="b4af4-102">S işlemi</span><span class="sxs-lookup"><span data-stu-id="b4af4-102">S operation</span></span>

<span data-ttu-id="b4af4-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="b4af4-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="b4af4-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4af4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4af4-105">S geçidini tek bir qubit 'e uygular.</span><span class="sxs-lookup"><span data-stu-id="b4af4-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="b4af4-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b4af4-106">Description</span></span>

<span data-ttu-id="b4af4-107">Bu işlem Unitary matrisi \ Begin{hizalaması} S \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix} tarafından benzetilir.</span><span class="sxs-lookup"><span data-stu-id="b4af4-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="b4af4-108">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="b4af4-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="b4af4-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="b4af4-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="b4af4-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b4af4-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b4af4-111">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="b4af4-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4af4-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4af4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

