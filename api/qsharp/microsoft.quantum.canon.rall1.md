---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1 işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 45892f9811faf56d7b9a0eb34e4bde0a32d5586d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728466"
---
# <a name="rall1-operation"></a><span data-ttu-id="1bfad-102">RAll1 işlemi</span><span class="sxs-lookup"><span data-stu-id="1bfad-102">RAll1 operation</span></span>

<span data-ttu-id="1bfad-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1bfad-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1bfad-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1bfad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1bfad-105">Bir aşama kaydırma işlemi gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="1bfad-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="1bfad-106">$R = \boldone-(1-e ^ {i \ Phi}) \ket{1\cnoktalar 1} \bra{1\cnoktalar 1} $.</span><span class="sxs-lookup"><span data-stu-id="1bfad-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1bfad-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="1bfad-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="1bfad-108">Aşama: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1bfad-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1bfad-109">$ \Ph{1\cnoktalar 1} \bra{1\cnoktalar 1} $ için $ \phi $ aşaması uygulandı.</span><span class="sxs-lookup"><span data-stu-id="1bfad-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1bfad-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1bfad-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1bfad-111">Durumu $R $ ile döndürüldüğü kayıt.</span><span class="sxs-lookup"><span data-stu-id="1bfad-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1bfad-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1bfad-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

