---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 9623d6d881f1f0ec048c3a951fe259bdfac84766
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202031"
---
# <a name="dumpregister-function"></a><span data-ttu-id="6c243-102">DumpRegister işlevi</span><span class="sxs-lookup"><span data-stu-id="6c243-102">DumpRegister function</span></span>

<span data-ttu-id="6c243-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6c243-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6c243-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6c243-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6c243-105">Geçerli hedef makinenin belirtilen qubits ile ilişkili durumunun dökümünü yapar.</span><span class="sxs-lookup"><span data-stu-id="6c243-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6c243-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6c243-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="6c243-107">Konum: 'T</span><span class="sxs-lookup"><span data-stu-id="6c243-107">location : 'T</span></span>

<span data-ttu-id="6c243-108">Durumun dökümünün nerede oluşturulacağı hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="6c243-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="6c243-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6c243-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6c243-110">Raporlanacak qubits listesi.</span><span class="sxs-lookup"><span data-stu-id="6c243-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6c243-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6c243-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="6c243-112">Yok.</span><span class="sxs-lookup"><span data-stu-id="6c243-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6c243-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="6c243-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6c243-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="6c243-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="6c243-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6c243-115">Remarks</span></span>

<span data-ttu-id="6c243-116">Bu yöntem, belirtilen qubits durumuyla ilişkili bilgilerin bir dosya veya başka bir konumda dökümünü yapmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="6c243-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="6c243-117">Oluşturulan gerçek bilgiler ve semantiği `location` her bir hedef makineye özeldir.</span><span class="sxs-lookup"><span data-stu-id="6c243-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="6c243-118">Ancak, konum () olarak boş bir tanımlama grubu sağlamak, `()` genellikle çıktıyı konsola oluşturma anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="6c243-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="6c243-119">Bu yöntem, hisse geliştirme seti 'nin bir parçası olarak dağıtılan yerel tam durum simülatörü için, söz konusu qubits 'in durumunu (karşılık gelen alt sistemin Wave işlevi), her bir öğenin karşılık gelen durumu ölçme olasılığının uyumlu olmasını temsil ettiği bir dosyanın yolunu içeren bir dize bekler.</span><span class="sxs-lookup"><span data-stu-id="6c243-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="6c243-120">Verilen qubits, başka bir qubitle ayrılarak ve durumları ayrılacaksa, yalnızca qubits 'in bir şekilde ayrılmış olduğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="6c243-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>