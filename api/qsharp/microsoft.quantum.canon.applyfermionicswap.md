---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Applyfermıonicswap işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729618"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="bb809-102">Applyfermıonicswap işlemi</span><span class="sxs-lookup"><span data-stu-id="bb809-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="bb809-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bb809-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bb809-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb809-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb809-105">Fermıonic SWAP 'ı uygular.</span><span class="sxs-lookup"><span data-stu-id="bb809-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="bb809-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bb809-106">Description</span></span>

<span data-ttu-id="bb809-107">Bu aslında, her iki qubit de 1s ise-1 Genel aşamasını uygularken qubits 'i değiştirir.</span><span class="sxs-lookup"><span data-stu-id="bb809-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="bb809-108">Orbitleri, simetrik olmayan bir şekilde korur.</span><span class="sxs-lookup"><span data-stu-id="bb809-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="bb809-109">Daha fazla bilgi edinmek için bkz. .</span><span class="sxs-lookup"><span data-stu-id="bb809-109">See  for more information.</span></span>

<span data-ttu-id="bb809-110">Bu işlem, Unitary işleci \ Begin{hizalaması} f_ {Swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 0 & 0 & \\ \\ 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix} tarafından temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="bb809-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="bb809-111">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="bb809-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="bb809-112">Giriş</span><span class="sxs-lookup"><span data-stu-id="bb809-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="bb809-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bb809-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bb809-114">Takas edilecek ilk qubit.</span><span class="sxs-lookup"><span data-stu-id="bb809-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="bb809-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bb809-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bb809-116">Takas edilecek ikinci qubit.</span><span class="sxs-lookup"><span data-stu-id="bb809-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bb809-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bb809-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="bb809-118">Referanslar</span><span class="sxs-lookup"><span data-stu-id="bb809-118">References</span></span>

- [<span data-ttu-id="bb809-119">*Ryan Bebush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic kanal* , arxıv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="bb809-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="bb809-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bb809-120">See Also</span></span>

- [<span data-ttu-id="bb809-121">Microsoft. hisse. Intrinsic. SWAP</span><span class="sxs-lookup"><span data-stu-id="bb809-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)