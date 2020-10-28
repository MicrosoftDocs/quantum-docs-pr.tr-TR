---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Squareı işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730463"
---
# <a name="squarei-operation"></a><span data-ttu-id="15fa7-102">Squareı işlemi</span><span class="sxs-lookup"><span data-stu-id="15fa7-102">SquareI operation</span></span>

<span data-ttu-id="15fa7-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="15fa7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="15fa7-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15fa7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15fa7-105">`xs` `result` , Başlangıçta sıfır olması gereken tamsayının karesini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="15fa7-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="15fa7-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="15fa7-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="15fa7-107">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="15fa7-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="15fa7-108">$n $-bit kare sayısı (Litttaendian)</span><span class="sxs-lookup"><span data-stu-id="15fa7-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="15fa7-109">Sonuç: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="15fa7-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="15fa7-110">$2N $-bit sonucu (Litttaendian), başlangıçta $ \ket $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="15fa7-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15fa7-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15fa7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="15fa7-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="15fa7-112">Remarks</span></span>

<span data-ttu-id="15fa7-113">Kareyi hesaplamak için standart bir kaydırma ve ekleme yaklaşımı kullanır.</span><span class="sxs-lookup"><span data-stu-id="15fa7-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="15fa7-114">, Düzenli bir çarpanı uygulamadan önce XS 'leri kopyalayan ve sonra kopyalama işlemini geri almadan önce XS 'i kopyalayan, düz iletme çözümüne kıyasla $n-$1 qubit tasarrufu sağlar.</span><span class="sxs-lookup"><span data-stu-id="15fa7-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>