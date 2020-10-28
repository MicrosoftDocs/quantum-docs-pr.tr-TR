---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727050"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="e1f5a-102">InjectPi4YRotation işlemi</span><span class="sxs-lookup"><span data-stu-id="e1f5a-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="e1f5a-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e1f5a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e1f5a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1f5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1f5a-105">Y ekseni hakkında π/4 ile tek bir qubit döndürür.</span><span class="sxs-lookup"><span data-stu-id="e1f5a-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="e1f5a-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e1f5a-106">Description</span></span>

<span data-ttu-id="e1f5a-107">Hakkında π/4 döndürme gerçekleştirir `Y` .</span><span class="sxs-lookup"><span data-stu-id="e1f5a-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="e1f5a-108">Döndürme, bir sihirli durum tüketerek gerçekleştirilir; diğer bir deyişle, $ $ \begin{hizalaması} \cos\frac{\pi} {8} {0} \tus+ \sin \ FRAC{\pi} {8} \tusöğesinin bir kopyasıdır {1} .</span><span class="sxs-lookup"><span data-stu-id="e1f5a-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="e1f5a-109">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="e1f5a-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="e1f5a-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="e1f5a-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="e1f5a-111">veri: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e1f5a-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e1f5a-112">$ \Pi/$4 ile $Y $ hakkında bir qubit döndürülür.</span><span class="sxs-lookup"><span data-stu-id="e1f5a-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="e1f5a-113">Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e1f5a-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e1f5a-114">Başlangıçta Magic durumunda bir qubit.</span><span class="sxs-lookup"><span data-stu-id="e1f5a-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="e1f5a-115">Bu işlemin aşağıdaki uygulaması `magic` $ \ket {0} $ durumuna döndürülür.</span><span class="sxs-lookup"><span data-stu-id="e1f5a-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1f5a-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1f5a-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e1f5a-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e1f5a-117">Remarks</span></span>

<span data-ttu-id="e1f5a-118">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="e1f5a-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="e1f5a-119">ve</span><span class="sxs-lookup"><span data-stu-id="e1f5a-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="e1f5a-120">Bu işlem, `Adjoint` functor 'ı destekler, bu durumda aynı sihirli durum tüketilen, ancak veri qubit üzerindeki etki bir $-\ Pi/4 $ $Y $-rotadır.</span><span class="sxs-lookup"><span data-stu-id="e1f5a-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>