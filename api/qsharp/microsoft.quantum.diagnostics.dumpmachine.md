---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727289"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="066a6-102">DumpMachine işlevi</span><span class="sxs-lookup"><span data-stu-id="066a6-102">DumpMachine function</span></span>

<span data-ttu-id="066a6-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="066a6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="066a6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="066a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="066a6-105">Geçerli hedef makinenin durumunu döker.</span><span class="sxs-lookup"><span data-stu-id="066a6-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="066a6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="066a6-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="066a6-107">Konum: 'T</span><span class="sxs-lookup"><span data-stu-id="066a6-107">location : 'T</span></span>

<span data-ttu-id="066a6-108">Makinenin dökümünü oluşturma hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="066a6-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="066a6-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="066a6-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="066a6-110">Yok.</span><span class="sxs-lookup"><span data-stu-id="066a6-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="066a6-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="066a6-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="066a6-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="066a6-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="066a6-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="066a6-113">Remarks</span></span>

<span data-ttu-id="066a6-114">Bu yöntem, hedef makinenin geçerli durumu hakkındaki bilgilerin bir dosyaya veya başka bir konuma dökümünü sağlar.</span><span class="sxs-lookup"><span data-stu-id="066a6-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="066a6-115">Oluşturulan gerçek bilgiler ve semantiği `location` her bir hedef makineye özeldir.</span><span class="sxs-lookup"><span data-stu-id="066a6-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="066a6-116">Ancak, bir konum () olarak boş bir tanımlama grubu sağlamak `()` ya da yalnızca `location` parametresi atlanırsa, genellikle çıktıyı konsola oluşturma anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="066a6-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="066a6-117">Bu yöntem, hisse geliştirme seti 'nin bir parçası olarak dağıtılan yerel tam durum simülatörü için, her bir öğenin karşılık gelen durumu ölçme olasılığının uyumlu olduğunu gösterdiği bir dosyanın yolunu içeren bir dosyanın yolunu içeren bir dize bekler.</span><span class="sxs-lookup"><span data-stu-id="066a6-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>