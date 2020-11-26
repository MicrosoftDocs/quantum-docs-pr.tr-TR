---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: df00c7572d909a67ec658bc8dccaf0e338afe5c5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200756"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="c343c-102">KnillDistill işlemi</span><span class="sxs-lookup"><span data-stu-id="c343c-102">KnillDistill operation</span></span>

<span data-ttu-id="c343c-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c343c-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c343c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c343c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c343c-105">Knill Magic State deneyimlerinin algoritmasını uygular.</span><span class="sxs-lookup"><span data-stu-id="c343c-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="c343c-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c343c-106">Description</span></span>

<span data-ttu-id="c343c-107">Bir sihirli durum $ $ \begin{hizalaması} \cos\frac{\pi} {8} {0} \tus+ \sin \ FRAC{\pi} {8} \kovaryans {1} \ End{hizalaması}, $ $ ' nin yaklaşık 15 ' i, daha yüksek kaliteli bir kopya veriyor.</span><span class="sxs-lookup"><span data-stu-id="c343c-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="c343c-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="c343c-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="c343c-109">Kabaghmagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c343c-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c343c-110">Bir sihirli durumun yaklaşık kopyalarını içeren on beş qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="c343c-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="c343c-111">Bu geri yükleme yordamının aşağıdaki uygulaması, `roughMagic[0]` daha yüksek kaliteli bir kopya içerir ve kaydın geri kalanı $ \ket{00\cnoktalara 0} $ duruma sıfırlanır.</span><span class="sxs-lookup"><span data-stu-id="c343c-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c343c-112">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c343c-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c343c-113">`true`Daha sonra, başarılı olan yordam ve daha yüksek kaliteli kopya kabul edilmelidir.</span><span class="sxs-lookup"><span data-stu-id="c343c-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="c343c-114">Eğer `false` yordam başarısız olursa ve kaydın durumu tanımsız olarak düşünülmelidir.</span><span class="sxs-lookup"><span data-stu-id="c343c-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="c343c-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c343c-115">Remarks</span></span>

<span data-ttu-id="c343c-116">Knill algoritmasını izliyoruz.</span><span class="sxs-lookup"><span data-stu-id="c343c-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="c343c-117">Ancak, mevcut uygulama çok fazla qubit kullandığından en iyi şekilde sürer.</span><span class="sxs-lookup"><span data-stu-id="c343c-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="c343c-118">Sihirli durumlar bu yordama eklenir ve bu durumda daha iyi protokoller vardır.</span><span class="sxs-lookup"><span data-stu-id="c343c-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="c343c-119">Başvurular</span><span class="sxs-lookup"><span data-stu-id="c343c-119">References</span></span>

- [<span data-ttu-id="c343c-120">Knill</span><span class="sxs-lookup"><span data-stu-id="c343c-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)