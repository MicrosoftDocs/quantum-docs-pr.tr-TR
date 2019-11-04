---
title: Hisse geliştirme seti tam durum simülatörü | Microsoft Docs
description: Microsoft 'un hisse geliştirme seti tam durum simülatörünü genel bakış
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184687"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="cc86e-103">Hisse geliştirme seti tam durum simülatörü</span><span class="sxs-lookup"><span data-stu-id="cc86e-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="cc86e-104">Hisse geliştirme seti, Microsoft Research 'tan [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) ile benzer bir tam durum hisse Benzetici sağlar.</span><span class="sxs-lookup"><span data-stu-id="cc86e-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="cc86e-105">Bu Benzetici, bilgisayarınızda Q # dilinde yazılan hisse algoritmaları yürütmek ve hatalarını ayıklamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="cc86e-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="cc86e-106">Bu hisse Benzetici, `QuantumSimulator` sınıfı aracılığıyla sunulur.</span><span class="sxs-lookup"><span data-stu-id="cc86e-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="cc86e-107">Simülatörü kullanmak için, bu sınıfın bir örneğini oluşturun ve bunu, diğer parametrelerin geri kalanında birlikte yürütmek istediğiniz hisse `Run` yöntemine geçirin:</span><span class="sxs-lookup"><span data-stu-id="cc86e-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="cc86e-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="cc86e-108">IDisposable</span></span>

<span data-ttu-id="cc86e-109">`QuantumSimulator` sınıfı <xref:System.IDisposable>uygular, bu nedenle simülatör örneği artık kullanılmıyordu `Dispose` yöntemi çağrılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cc86e-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="cc86e-110">Bunu yapmanın en iyi yolu, simülatörü Yukarıdaki örnekte olduğu gibi bir `using` ifadesine sarmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cc86e-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="cc86e-111">Çekirdek</span><span class="sxs-lookup"><span data-stu-id="cc86e-111">Seed</span></span>

<span data-ttu-id="cc86e-112">`QuantumSimulator`, hisse rastlılığını taklit etmek için rastgele bir sayı Oluşturucu kullanır.</span><span class="sxs-lookup"><span data-stu-id="cc86e-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="cc86e-113">Sınama amacıyla, bazen belirleyici sonuçlar elde etmek yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="cc86e-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="cc86e-114">Bu, `randomNumberGeneratorSeed` parametresi aracılığıyla `QuantumSimulator`oluşturucusunda rastgele numara Oluşturucu için bir çekirdek sağlanarak gerçekleştirilebilir:</span><span class="sxs-lookup"><span data-stu-id="cc86e-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="cc86e-115">Akışları</span><span class="sxs-lookup"><span data-stu-id="cc86e-115">Threads</span></span>

<span data-ttu-id="cc86e-116">`QuantumSimulator`, gereken doğrusal algeköşeli paralel hale getirmek için [OpenMP](http://www.openmp.org/) kullanır.</span><span class="sxs-lookup"><span data-stu-id="cc86e-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="cc86e-117">Varsayılan olarak OpenMP, tüm kullanılabilir donanım iş parçacıklarını kullanır, bu da az sayıda qubit içeren programların, gerçek işi dyacağı için gereken koordinasyonuna yavaş çalışacağı anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="cc86e-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="cc86e-118">Bu, ortam değişkeni `OMP_NUM_THREADS` küçük bir sayı ayarlanarak düzeltilebilir.</span><span class="sxs-lookup"><span data-stu-id="cc86e-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="cc86e-119">En çok kaba bir kural olarak, 1 iş parçacığı yaklaşık 4 qubit 'e kadar iyidir ve daha sonra, bu, algoritmanız için büyük ölçüde bağımlı olsa da, qubit başına ek bir iş parçacığı iyidir.</span><span class="sxs-lookup"><span data-stu-id="cc86e-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

