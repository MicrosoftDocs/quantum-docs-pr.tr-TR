---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Applyfermıonicswap işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218810"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="973e0-102">Applyfermıonicswap işlemi</span><span class="sxs-lookup"><span data-stu-id="973e0-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="973e0-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="973e0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="973e0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="973e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="973e0-105">Fermıonic SWAP 'ı uygular.</span><span class="sxs-lookup"><span data-stu-id="973e0-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="973e0-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="973e0-106">Description</span></span>

<span data-ttu-id="973e0-107">Bu aslında, her iki qubit de 1s ise-1 Genel aşamasını uygularken qubits 'i değiştirir.</span><span class="sxs-lookup"><span data-stu-id="973e0-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="973e0-108">Orbitleri, simetrik olmayan bir şekilde korur.</span><span class="sxs-lookup"><span data-stu-id="973e0-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="973e0-109">Daha fazla bilgi edinmek için bkz. .</span><span class="sxs-lookup"><span data-stu-id="973e0-109">See  for more information.</span></span>

<span data-ttu-id="973e0-110">Bu işlem, Unitary işleci \ Begin{hizalaması} f_ {Swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 0 & 0 & \\ \\ 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix} tarafından temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="973e0-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="973e0-111">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="973e0-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="973e0-112">Giriş</span><span class="sxs-lookup"><span data-stu-id="973e0-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="973e0-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="973e0-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="973e0-114">Takas edilecek ilk qubit.</span><span class="sxs-lookup"><span data-stu-id="973e0-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="973e0-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="973e0-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="973e0-116">Takas edilecek ikinci qubit.</span><span class="sxs-lookup"><span data-stu-id="973e0-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="973e0-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="973e0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="973e0-118">Başvurular</span><span class="sxs-lookup"><span data-stu-id="973e0-118">References</span></span>

- [<span data-ttu-id="973e0-119">*Ryan Bebush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic kanal*, arxıv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="973e0-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="973e0-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="973e0-120">See Also</span></span>

- [<span data-ttu-id="973e0-121">Microsoft. hisse. Intrinsic. SWAP</span><span class="sxs-lookup"><span data-stu-id="973e0-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)