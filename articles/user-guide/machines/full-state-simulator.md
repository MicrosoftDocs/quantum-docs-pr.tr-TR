---
title: Tam durum hisse simülatör-hisse geliştirme seti
description: 'Q # programlarınızı Microsoft Quantum Development Kit tam durum benzeticisinde çalıştırmayı öğrenin.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: 563fdbd2a45461d112e4c46651eddd75c6fc3db2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871187"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="5c42c-103">Hisse geliştirme seti (QDK) tam durum simülatör</span><span class="sxs-lookup"><span data-stu-id="5c42c-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="5c42c-104">QDK, yerel bilgisayarınızdaki bir hisse makinenizin benzetimini yapan tam bir durum simülatörü sağlar.</span><span class="sxs-lookup"><span data-stu-id="5c42c-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="5c42c-105">En fazla 30 qubit kullanarak Q # dilinde yazılan hisse algoritmaları çalıştırmak ve hatalarını ayıklamak için tam durum simülatörü ' ni kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5c42c-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="5c42c-106">Tam durum simülatörü, Microsoft Research 'ın [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) platformunda kullanılan hisse simülatcıya benzer.</span><span class="sxs-lookup"><span data-stu-id="5c42c-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="5c42c-107">Tam durum simülatörü çağırma ve çalıştırma</span><span class="sxs-lookup"><span data-stu-id="5c42c-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="5c42c-108">Sınıf aracılığıyla tam durum simülatörünü kullanıma sunacaksınız `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="5c42c-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="5c42c-109">Daha fazla ayrıntı için bkz. [bir Q # programını çalıştırma yolları](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="5c42c-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="5c42c-110">C 'den simülatör çağrılıyor #</span><span class="sxs-lookup"><span data-stu-id="5c42c-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="5c42c-111">Sınıfın bir örneğini oluşturun `QuantumSimulator` ve sonra `Run` ek parametrelerle birlikte bir hisse işlem yöntemine geçirin.</span><span class="sxs-lookup"><span data-stu-id="5c42c-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="5c42c-112">`QuantumSimulator`Sınıfı <xref:System.IDisposable> arabirimini uyguladığından, `Dispose` simülatör örneğine gerek duyduktan sonra yöntemini çağırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="5c42c-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="5c42c-113">Bunu yapmanın en iyi yolu, simülatör bildirimini ve işlemlerini yöntemi otomatik olarak çağıran bir [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) ifadesiyle sarmalıdır `Dispose` .</span><span class="sxs-lookup"><span data-stu-id="5c42c-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="5c42c-114">Python 'dan simülatör çağrılıyor</span><span class="sxs-lookup"><span data-stu-id="5c42c-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="5c42c-115">Q # Python kitaplığındaki, içeri aktarılan Q # işlemiyle [Benzetim ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) yöntemini kullanın:</span><span class="sxs-lookup"><span data-stu-id="5c42c-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="5c42c-116">Komut satırından Benzetici çağırma</span><span class="sxs-lookup"><span data-stu-id="5c42c-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="5c42c-117">Bir Q # programını komut satırından çalıştırırken, tam durum simülatör varsayılan hedef makinedir.</span><span class="sxs-lookup"><span data-stu-id="5c42c-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="5c42c-118">İsteğe bağlı olarak, istenen hedef makineyi belirtmek için **--simülatör** (veya **-s** Shortcut) parametresini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5c42c-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="5c42c-119">Aşağıdaki komutlardan her ikisi de tam durum simülatörü kullanarak bir program çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="5c42c-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="5c42c-120">Juptyer not defterlerinden simülatörü çağırma</span><span class="sxs-lookup"><span data-stu-id="5c42c-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="5c42c-121">Q # işlemini çalıştırmak için IQ # Magic komutu [% benzetimini](xref:microsoft.quantum.iqsharp.magic-ref.simulate) kullanın.</span><span class="sxs-lookup"><span data-stu-id="5c42c-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="5c42c-122">Simülatör dengeli</span><span class="sxs-lookup"><span data-stu-id="5c42c-122">Seeding the simulator</span></span>

<span data-ttu-id="5c42c-123">Varsayılan olarak, tam durum simülatörü, hisse miktarı benzetimi için rastgele bir sayı Oluşturucu kullanır.</span><span class="sxs-lookup"><span data-stu-id="5c42c-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="5c42c-124">Sınama amacıyla, bazen belirleyici sonuçlar elde etmek yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="5c42c-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="5c42c-125">Bir C# programında, parametresi aracılığıyla oluşturucuda rastgele numara Oluşturucu için bir çekirdek sağlayarak bunu yapabilirsiniz `QuantumSimulator` `randomNumberGeneratorSeed` .</span><span class="sxs-lookup"><span data-stu-id="5c42c-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="5c42c-126">İş parçacıklarını yapılandırma</span><span class="sxs-lookup"><span data-stu-id="5c42c-126">Configuring threads</span></span>

<span data-ttu-id="5c42c-127">Tam durum simülatör, gereken doğrusal algeköşeli paralel hale getirmek için [OpenMP](http://www.openmp.org/) kullanır.</span><span class="sxs-lookup"><span data-stu-id="5c42c-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="5c42c-128">Varsayılan olarak, OpenMP, en az sayıda qubit olan programlar, gerçek işi dide gereken koordinasyon nedeniyle genellikle yavaş çalıştığı anlamına gelen tüm kullanılabilir donanım iş parçacıklarını kullanır.</span><span class="sxs-lookup"><span data-stu-id="5c42c-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="5c42c-129">Bu ayarı, ortam değişkenini `OMP_NUM_THREADS` küçük bir sayı olarak ayarlayarak giderebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5c42c-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="5c42c-130">Thumb kuralı olarak, bir iş parçacığını en fazla dört qubit ve daha sonra qubit başına bir ek iş parçacığı yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="5c42c-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="5c42c-131">Algoritmasına göre değişkeni ayarlamanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="5c42c-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c42c-132">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5c42c-132">See also</span></span>

- [<span data-ttu-id="5c42c-133">Hisse kaynağı tahmin aracı</span><span class="sxs-lookup"><span data-stu-id="5c42c-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="5c42c-134">Hisse Toffoli simülatör</span><span class="sxs-lookup"><span data-stu-id="5c42c-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="5c42c-135">Hisse izi izleme simülatörü</span><span class="sxs-lookup"><span data-stu-id="5c42c-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)