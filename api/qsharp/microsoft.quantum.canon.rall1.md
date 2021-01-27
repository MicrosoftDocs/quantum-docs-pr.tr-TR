---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1 işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: f4159a6cc0e0b4f18f418a53a309b5ce527b2608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852254"
---
# <a name="rall1-operation"></a><span data-ttu-id="eb90a-102">RAll1 işlemi</span><span class="sxs-lookup"><span data-stu-id="eb90a-102">RAll1 operation</span></span>

<span data-ttu-id="eb90a-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eb90a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eb90a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb90a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb90a-105">Bir aşama kaydırma işlemi gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="eb90a-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="eb90a-106">$R = \boldone-(1-e ^ {i \ Phi}) \ket{1\cnoktalar 1} \bra{1\cnoktalar 1} $.</span><span class="sxs-lookup"><span data-stu-id="eb90a-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="eb90a-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="eb90a-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="eb90a-108">Aşama: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eb90a-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eb90a-109">$ \Ph{1\cnoktalar 1} \bra{1\cnoktalar 1} $ için $ \phi $ aşaması uygulandı.</span><span class="sxs-lookup"><span data-stu-id="eb90a-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="eb90a-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eb90a-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eb90a-111">Durumu $R $ ile döndürüldüğü kayıt.</span><span class="sxs-lookup"><span data-stu-id="eb90a-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb90a-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb90a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

