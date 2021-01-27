---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825953"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="7d81a-102">InjectPi4YRotation işlemi</span><span class="sxs-lookup"><span data-stu-id="7d81a-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="7d81a-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7d81a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7d81a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d81a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d81a-105">Y ekseni hakkında π/4 ile tek bir qubit döndürür.</span><span class="sxs-lookup"><span data-stu-id="7d81a-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="7d81a-106">Description</span><span class="sxs-lookup"><span data-stu-id="7d81a-106">Description</span></span>

<span data-ttu-id="7d81a-107">Hakkında π/4 döndürme gerçekleştirir `Y` .</span><span class="sxs-lookup"><span data-stu-id="7d81a-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="7d81a-108">Döndürme, bir sihirli durum tüketerek gerçekleştirilir; diğer bir deyişle, $ $ \begin{hizalaması} \cos\frac{\pi} {8} {0} \tus+ \sin \ FRAC{\pi} {8} \tusöğesinin bir kopyasıdır {1} .</span><span class="sxs-lookup"><span data-stu-id="7d81a-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="7d81a-109">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="7d81a-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="7d81a-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="7d81a-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="7d81a-111">veri: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7d81a-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7d81a-112">$ \Pi/$4 ile $Y $ hakkında bir qubit döndürülür.</span><span class="sxs-lookup"><span data-stu-id="7d81a-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="7d81a-113">Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7d81a-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7d81a-114">Başlangıçta Magic durumunda bir qubit.</span><span class="sxs-lookup"><span data-stu-id="7d81a-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="7d81a-115">Bu işlemin aşağıdaki uygulaması `magic` $ \ket {0} $ durumuna döndürülür.</span><span class="sxs-lookup"><span data-stu-id="7d81a-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d81a-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d81a-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7d81a-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7d81a-117">Remarks</span></span>

<span data-ttu-id="7d81a-118">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="7d81a-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="7d81a-119">ve</span><span class="sxs-lookup"><span data-stu-id="7d81a-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="7d81a-120">Bu işlem, `Adjoint` functor 'ı destekler, bu durumda aynı sihirli durum tüketilen, ancak veri qubit üzerindeki etki bir $-\ Pi/4 $ $Y $-rotadır.</span><span class="sxs-lookup"><span data-stu-id="7d81a-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>