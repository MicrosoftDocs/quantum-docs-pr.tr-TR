---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: 579300d4efb9e22cb671fbb4bce0a6f72dd0e2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853411"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="02c64-102">DumpMachine işlevi</span><span class="sxs-lookup"><span data-stu-id="02c64-102">DumpMachine function</span></span>

<span data-ttu-id="02c64-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="02c64-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="02c64-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="02c64-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="02c64-105">Geçerli hedef makinenin durumunu döker.</span><span class="sxs-lookup"><span data-stu-id="02c64-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="02c64-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="02c64-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="02c64-107">Konum: 'T</span><span class="sxs-lookup"><span data-stu-id="02c64-107">location : 'T</span></span>

<span data-ttu-id="02c64-108">Makinenin dökümünü oluşturma hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="02c64-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="02c64-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="02c64-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="02c64-110">Yok.</span><span class="sxs-lookup"><span data-stu-id="02c64-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="02c64-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="02c64-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="02c64-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="02c64-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="02c64-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="02c64-113">Remarks</span></span>

<span data-ttu-id="02c64-114">Bu yöntem, hedef makinenin geçerli durumu hakkındaki bilgilerin bir dosyaya veya başka bir konuma dökümünü sağlar.</span><span class="sxs-lookup"><span data-stu-id="02c64-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="02c64-115">Oluşturulan gerçek bilgiler ve semantiği `location` her bir hedef makineye özeldir.</span><span class="sxs-lookup"><span data-stu-id="02c64-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="02c64-116">Ancak, bir konum () olarak boş bir tanımlama grubu sağlamak `()` ya da yalnızca `location` parametresi atlanırsa, genellikle çıktıyı konsola oluşturma anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="02c64-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="02c64-117">Bu yöntem, hisse geliştirme seti 'nin bir parçası olarak dağıtılan yerel tam durum simülatörü için, her bir öğenin karşılık gelen durumu ölçme olasılığının uyumlu olduğunu gösterdiği bir dosyanın yolunu içeren bir dosyanın yolunu içeren bir dize bekler.</span><span class="sxs-lookup"><span data-stu-id="02c64-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>