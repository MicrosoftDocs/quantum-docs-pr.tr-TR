---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859265"
---
# <a name="applyunitary-operation"></a><span data-ttu-id="3f7fb-102">ApplyUnitary işlemi</span><span class="sxs-lookup"><span data-stu-id="3f7fb-102">ApplyUnitary operation</span></span>

<span data-ttu-id="3f7fb-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="3f7fb-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="3f7fb-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3f7fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3f7fb-105">2 ^ n x 2 ^ n Unitary matrisi tarafından tanımlanan geçit uygular.</span><span class="sxs-lookup"><span data-stu-id="3f7fb-105">Applies gate defined by 2^n x 2^n unitary matrix.</span></span>

<span data-ttu-id="3f7fb-106">Matris Unitary değilse veya boyut yanlış ise başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="3f7fb-106">Fails if matrix is not unitary, or has wrong size.</span></span>

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3f7fb-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="3f7fb-107">Input</span></span>

### <a name="unitary--complex"></a><span data-ttu-id="3f7fb-108">Unitary: [karmaşık](xref:Microsoft.Quantum.Math.Complex)[] []</span><span class="sxs-lookup"><span data-stu-id="3f7fb-108">unitary : [Complex](xref:Microsoft.Quantum.Math.Complex)[][]</span></span>

<span data-ttu-id="3f7fb-109">2 ^ n x 2 ^ n Unitary, işlemi açıklayan matris.</span><span class="sxs-lookup"><span data-stu-id="3f7fb-109">2^n x 2^n unitary matrix describing the operation.</span></span>
<span data-ttu-id="3f7fb-110">Matris Unitary veya uygun boyutta değilse, bir özel durum oluşturur.</span><span class="sxs-lookup"><span data-stu-id="3f7fb-110">If matrix is not unitary or not of suitable size, throws an exception.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="3f7fb-111">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f7fb-111">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f7fb-112">İşlem-yazmaç uzunluğu için gereken qubitleri.</span><span class="sxs-lookup"><span data-stu-id="3f7fb-112">Qubits to which apply the operation - register of length n.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f7fb-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f7fb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

