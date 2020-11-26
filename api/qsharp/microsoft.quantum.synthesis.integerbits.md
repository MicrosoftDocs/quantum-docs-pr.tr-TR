---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Integerbits işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231101"
---
# <a name="integerbits-function"></a><span data-ttu-id="0878a-102">Integerbits işlevi</span><span class="sxs-lookup"><span data-stu-id="0878a-102">IntegerBits function</span></span>

<span data-ttu-id="0878a-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0878a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0878a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0878a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0878a-105">Tamsayının bit sayısının ayarlandığı tüm pozisyonları döndürür.</span><span class="sxs-lookup"><span data-stu-id="0878a-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="0878a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0878a-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="0878a-107">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0878a-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0878a-108">Negatif olmayan bir sayı.</span><span class="sxs-lookup"><span data-stu-id="0878a-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="0878a-109">Uzunluk: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0878a-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0878a-110">İkili genişletmesinde bit sayısı `value` .</span><span class="sxs-lookup"><span data-stu-id="0878a-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="0878a-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0878a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0878a-112">`value`Tüm bitleri konuma kadar ele almak için ikili genişlemesinde 1 olan tüm bit konumlarını (0 ' dan başlayarak) içeren bir dizi `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="0878a-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="0878a-113">Tüm pozisyonlar, dizi içinde artan bir düzende konuma göre sıralanır.</span><span class="sxs-lookup"><span data-stu-id="0878a-113">All positions are ordered in the array by position in an increasing order.</span></span>