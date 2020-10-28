---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Yaklaşık Teqft işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: ffa3a3737a43fbe6acc57700ae122a13586482e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728958"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="dd63c-102">Yaklaşık Teqft işlemi</span><span class="sxs-lookup"><span data-stu-id="dd63c-102">ApproximateQFT operation</span></span>

<span data-ttu-id="dd63c-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dd63c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dd63c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dd63c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dd63c-105">Yaklaşık hisse Fourier dönüştürmesinin (AQFT) bir hisse kaydına uygulanmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="dd63c-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="dd63c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="dd63c-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="dd63c-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd63c-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd63c-108">en fazla parametre, QFT devresi içinde gerçekleşen kontrol edilen Z-döndürme işleminin ayıklandığını belirler.</span><span class="sxs-lookup"><span data-stu-id="dd63c-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="dd63c-109">Bir ∈ {0.. n} ve k>a 'nın QFT devresi öğesinden kaldırıldığı tüm Z-Rod 'ler 2π/2k 'nin ayıklama düzeyini belirten bir parametre.</span><span class="sxs-lookup"><span data-stu-id="dd63c-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="dd63c-110">K >= log ₂ (n) + log ₂ (1/ε) + 3 ' ün bağlanabilir olduğu bilinmektedir | | QFT-AQFT | |<ε.</span><span class="sxs-lookup"><span data-stu-id="dd63c-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="dd63c-111">QS: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="dd63c-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="dd63c-112">Yaklaşık ortalama Fourier dönüştürmesinin uygulandığı n qubit 'in hisse kaydı.</span><span class="sxs-lookup"><span data-stu-id="dd63c-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd63c-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd63c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dd63c-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="dd63c-114">Remarks</span></span>

<span data-ttu-id="dd63c-115">AQFT, 2π/2k ve Hadamard Gates biçimindeki Z-dönüşü geçitleri gerektirir.</span><span class="sxs-lookup"><span data-stu-id="dd63c-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="dd63c-116">Giriş ve çıkışın big endian kodlamada kodlandığını kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="dd63c-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="dd63c-117">Referanslar</span><span class="sxs-lookup"><span data-stu-id="dd63c-117">References</span></span>

- [<span data-ttu-id="dd63c-118">*A. Roetteler, TH. Beth* , Uyg. Algeköşeli eng. Commun. Bilgi. 19 (3): 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="dd63c-118"> *M. Roetteler, Th. Beth* , Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="dd63c-119">*D. Coppersmith* arxıv: Quant-pH/sper1067v1</span><span class="sxs-lookup"><span data-stu-id="dd63c-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)