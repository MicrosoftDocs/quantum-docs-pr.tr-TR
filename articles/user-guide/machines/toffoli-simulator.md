---
title: Hisse Toffoli simülatör-hisse geliştirme seti
description: Milyonlarca qubitle kullanılabilecek özel bir amaç simülatörü olan Microsoft QDK Toffoli benzeticileri hakkında bilgi edinin.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6a0885035c12a99ae43533f04cdc95c5c529380a
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992232"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="83539-103">Hisse geliştirme seti (QDK) Toffoli simülatör</span><span class="sxs-lookup"><span data-stu-id="83539-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="83539-104">QDK Toffoli simülatörü, sınırlı bir kapsama sahip özel amaçlı bir Benzetici ve yalnızca `X` , `CNOT` ve çoklu denetimli `X` hisse operasyonlarını destekler.</span><span class="sxs-lookup"><span data-stu-id="83539-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="83539-105">Tüm klasik mantık ve hesaplamalar kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="83539-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="83539-106">Toffoli simülatör, [tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator)'nin işlevselliğinde daha kısıtlı olsa da, bu, en fazla qubit benzetimi yapabilmesinin avantajına sahiptir.</span><span class="sxs-lookup"><span data-stu-id="83539-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="83539-107">Toffoli simülatörü milyonlarca qubit ile birlikte kullanılabilir, ancak tam durum simülatörü yaklaşık 30 qubitle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="83539-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="83539-108">Bu, örneğin, Boole işlevlerini değerlendiren Oracles ile, sınırlı desteklenen algoritmalar kümesi kullanılarak uygulanamazlar ve çok sayıda qubit üzerinde test edilebilir.</span><span class="sxs-lookup"><span data-stu-id="83539-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="83539-109">Toffoli simülatörü çağırma</span><span class="sxs-lookup"><span data-stu-id="83539-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="83539-110">Toffoli simülatörünü sınıfı aracılığıyla kullanıma sunun `ToffoliSimulator` .</span><span class="sxs-lookup"><span data-stu-id="83539-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="83539-111">Daha fazla bilgi için bkz. [ Q# Program çalıştırma yolları](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="83539-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="83539-112">C Toffoli simülatörü çağırma #</span><span class="sxs-lookup"><span data-stu-id="83539-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="83539-113">Diğer hedef makinelerde olduğu gibi, önce `ToffoliSimulator` sınıfının bir örneğini oluşturup ardından bunu bir işlemin `Run` metodunun ilk parametresi olarak geçirirsiniz.</span><span class="sxs-lookup"><span data-stu-id="83539-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="83539-114">`QuantumSimulator` sınıfının aksine, `ToffoliSimulator` sınıfının <xref:System.IDisposable> arabirimini uygulamadığını ve bu nedenle bunu bir `using` deyimi içine almanız gerekmediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="83539-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="83539-115">Python 'dan Toffoli simülatörü çağırma</span><span class="sxs-lookup"><span data-stu-id="83539-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="83539-116">Python kitaplığındaki [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) yöntemini içeri aktarılan Q# işlemle kullanın:</span><span class="sxs-lookup"><span data-stu-id="83539-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="83539-117">Komut satırından Toffoli simülatörü çağırma</span><span class="sxs-lookup"><span data-stu-id="83539-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="83539-118">Q#Komut satırından bir program çalıştırırken, Toffoli simülatör hedef makinesini belirtmek için **--simülatör** (veya **-s** Shortcut) parametresini kullanın.</span><span class="sxs-lookup"><span data-stu-id="83539-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="83539-119">Aşağıdaki komut Estimator kaynaklarını kullanarak bir program çalıştırır:</span><span class="sxs-lookup"><span data-stu-id="83539-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="83539-120">Juptyer not defterlerinden Toffoli simülatörü çağırma</span><span class="sxs-lookup"><span data-stu-id="83539-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="83539-121">Q#İşlemi çalıştırmak için I Magic komutu [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) kullanın Q# .</span><span class="sxs-lookup"><span data-stu-id="83539-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="83539-122">Desteklenen işlemler</span><span class="sxs-lookup"><span data-stu-id="83539-122">Supported operations</span></span>

<span data-ttu-id="83539-123">Toffoli simülatör şunları destekler:</span><span class="sxs-lookup"><span data-stu-id="83539-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="83539-124">`R` `Exp` Ortaya çıkan işlem, `X` ya da kimlik matrisine eşit olduğunda, ve gibi geçen Paulis 'ler.</span><span class="sxs-lookup"><span data-stu-id="83539-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="83539-125">Ölçüm ve [onaylama](xref:microsoft.quantum.diagnostics.assertmeasurement) işlemleri, ancak yalnızca Pauli `Z` temelinde.</span><span class="sxs-lookup"><span data-stu-id="83539-125">Measurement and [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="83539-126">Ölçüm işleminin olasılığının her zaman **0** ya da **1**olduğunu unutmayın; Toffoli benzeticisinde rastgele bir değer yoktur.</span><span class="sxs-lookup"><span data-stu-id="83539-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="83539-127">`DumpMachine` ve `DumpRegister` işlevleri.</span><span class="sxs-lookup"><span data-stu-id="83539-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="83539-128">Her iki işlev de `Z` her bir qubit, satır başına bir qubit olmak üzere, her bir qubit için geçerli</span><span class="sxs-lookup"><span data-stu-id="83539-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="83539-129">Qubits sayısını belirtme</span><span class="sxs-lookup"><span data-stu-id="83539-129">Specifying the number of qubits</span></span>

<span data-ttu-id="83539-130">Varsayılan olarak, bir `ToffoliSimulator` örnek 65.536 qubit için alan ayırır.</span><span class="sxs-lookup"><span data-stu-id="83539-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="83539-131">Algoritmanız bundan daha fazla qubit gerektiriyorsa, oluşturucuya parametresi için bir değer sağlayarak qubit sayısını belirtebilirsiniz `qubitCount` .</span><span class="sxs-lookup"><span data-stu-id="83539-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="83539-132">Her ek qubit yalnızca bir baytlık bellek gerektirir, bu nedenle ihtiyaç duyacağınız qubit sayısını fazla tahmin etmek için önemli bir maliyet yoktur.</span><span class="sxs-lookup"><span data-stu-id="83539-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="83539-133">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="83539-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="83539-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="83539-134">See also</span></span>

- [<span data-ttu-id="83539-135">Hisse kaynağı Estimator</span><span class="sxs-lookup"><span data-stu-id="83539-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="83539-136">Hisse Izi Izleme simülatörü</span><span class="sxs-lookup"><span data-stu-id="83539-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="83539-137">Hisse dolu durum simülatörü</span><span class="sxs-lookup"><span data-stu-id="83539-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 