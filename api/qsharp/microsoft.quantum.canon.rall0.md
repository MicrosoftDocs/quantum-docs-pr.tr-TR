---
uid: Microsoft.Quantum.Canon.RAll0
title: RAll0 işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 660e6633df6750747963d41a6ff28a4fd4b02d4e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840242"
---
# <a name="rall0-operation"></a><span data-ttu-id="fedf3-102">RAll0 işlemi</span><span class="sxs-lookup"><span data-stu-id="fedf3-102">RAll0 operation</span></span>

<span data-ttu-id="fedf3-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fedf3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fedf3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fedf3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fedf3-105">Bir aşama kaydırma işlemi gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="fedf3-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="fedf3-106">$R = \boldone-(1-e ^ {i \ Phi}) \ket{0\cnoktalar 0} \bra{0\cnoktalar 0} $.</span><span class="sxs-lookup"><span data-stu-id="fedf3-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fedf3-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="fedf3-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="fedf3-108">Aşama: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fedf3-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fedf3-109">$ \Ph{0\cnoktalara 0} \bra{0\cnoktalar 0} $ için $ \phi $ aşaması uygulandı.</span><span class="sxs-lookup"><span data-stu-id="fedf3-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fedf3-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fedf3-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fedf3-111">Durumu $R $ ile döndürüldüğü kayıt.</span><span class="sxs-lookup"><span data-stu-id="fedf3-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fedf3-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fedf3-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="fedf3-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fedf3-113">See Also</span></span>

- [<span data-ttu-id="fedf3-114">Microsoft. hisse. Canon. RAll1</span><span class="sxs-lookup"><span data-stu-id="fedf3-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)