---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Integerbits işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855412"
---
# <a name="integerbits-function"></a><span data-ttu-id="73cb1-102">Integerbits işlevi</span><span class="sxs-lookup"><span data-stu-id="73cb1-102">IntegerBits function</span></span>

<span data-ttu-id="73cb1-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="73cb1-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="73cb1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73cb1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73cb1-105">Tamsayının bit sayısının ayarlandığı tüm pozisyonları döndürür.</span><span class="sxs-lookup"><span data-stu-id="73cb1-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="73cb1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="73cb1-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="73cb1-107">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="73cb1-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="73cb1-108">Negatif olmayan bir sayı.</span><span class="sxs-lookup"><span data-stu-id="73cb1-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="73cb1-109">Uzunluk: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="73cb1-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="73cb1-110">İkili genişletmesinde bit sayısı `value` .</span><span class="sxs-lookup"><span data-stu-id="73cb1-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="73cb1-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="73cb1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="73cb1-112">`value`Tüm bitleri konuma kadar ele almak için ikili genişlemesinde 1 olan tüm bit konumlarını (0 ' dan başlayarak) içeren bir dizi `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="73cb1-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="73cb1-113">Tüm pozisyonlar, dizi içinde artan bir düzende konuma göre sıralanır.</span><span class="sxs-lookup"><span data-stu-id="73cb1-113">All positions are ordered in the array by position in an increasing order.</span></span>

## <a name="example"></a><span data-ttu-id="73cb1-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="73cb1-114">Example</span></span>

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```