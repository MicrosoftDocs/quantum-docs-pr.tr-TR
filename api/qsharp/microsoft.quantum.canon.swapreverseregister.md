---
uid: Microsoft.Quantum.Canon.SwapReverseRegister
title: SwapReverseRegister işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: SwapReverseRegister
qsharp.summary: Uses SWAP gates to Reversed the order of the qubits in a register.
ms.openlocfilehash: 9df62c4ef97a186b274a62bd493fa9e7bbb74fa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204989"
---
# <a name="swapreverseregister-operation"></a><span data-ttu-id="0758b-102">SwapReverseRegister işlemi</span><span class="sxs-lookup"><span data-stu-id="0758b-102">SwapReverseRegister operation</span></span>

<span data-ttu-id="0758b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0758b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0758b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0758b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0758b-105">Bir kayıttaki qubits 'in sırasını tersine getirmek için takas kapıları kullanır.</span><span class="sxs-lookup"><span data-stu-id="0758b-105">Uses SWAP gates to Reversed the order of the qubits in a register.</span></span>

```qsharp
operation SwapReverseRegister (register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0758b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0758b-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="0758b-107">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0758b-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0758b-108">TAKAS kapıları kullanılarak ters kullanılması gereken qubits sıralaması</span><span class="sxs-lookup"><span data-stu-id="0758b-108">The qubits order of which should be reversed using SWAP gates</span></span>



## <a name="output--unit"></a><span data-ttu-id="0758b-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0758b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

