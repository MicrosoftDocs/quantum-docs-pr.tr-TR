---
title: Tam durum simülatör
description: 'Q # programlarınızı Microsoft Quantum Development Kit tam durum Benzeticisinde çalıştırmayı öğrenin.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275647"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="03e77-103">Hisse geliştirme seti tam durum simülatörü</span><span class="sxs-lookup"><span data-stu-id="03e77-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="03e77-104">Hisse geliştirme seti, Microsoft Research 'tan [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) ile benzer bir tam durum hisse Benzetici sağlar.</span><span class="sxs-lookup"><span data-stu-id="03e77-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="03e77-105">Bu Benzetici, bilgisayarınızda Q # dilinde yazılan hisse algoritmaları yürütmek ve hatalarını ayıklamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="03e77-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="03e77-106">Bu hisse Benzetici, sınıfı aracılığıyla sunulur `QuantumSimulator` .</span><span class="sxs-lookup"><span data-stu-id="03e77-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="03e77-107">Simülatörü kullanmak için, bu sınıfın bir örneğini oluşturun ve `Run` diğer parametrelerin geri kalanında birlikte yürütmek istediğiniz hisse işlem yöntemine geçirin:</span><span class="sxs-lookup"><span data-stu-id="03e77-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="03e77-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="03e77-108">IDisposable</span></span>

<span data-ttu-id="03e77-109">`QuantumSimulator`Sınıfı uygular <xref:System.IDisposable> , bu nedenle `Dispose` Benzetici örneği artık kullanılmaması durumunda yöntem çağrılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="03e77-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="03e77-110">Bunu yapmanın en iyi yolu, simülatörünü `using` Yukarıdaki örnekte olduğu gibi bir deyime sarmalıdır.</span><span class="sxs-lookup"><span data-stu-id="03e77-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="03e77-111">Çekirdek</span><span class="sxs-lookup"><span data-stu-id="03e77-111">Seed</span></span>

<span data-ttu-id="03e77-112">, `QuantumSimulator` Hisse rastlılığını taklit etmek için rastgele bir sayı Oluşturucu kullanır.</span><span class="sxs-lookup"><span data-stu-id="03e77-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="03e77-113">Sınama amacıyla, bazen belirleyici sonuçlar elde etmek yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="03e77-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="03e77-114">Bu, `QuantumSimulator` parametresi aracılığıyla kurucusundaki rastgele sayı üreticisi için bir çekirdek sağlanarak gerçekleştirilebilir `randomNumberGeneratorSeed` :</span><span class="sxs-lookup"><span data-stu-id="03e77-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="03e77-115">İş Parçacıkları</span><span class="sxs-lookup"><span data-stu-id="03e77-115">Threads</span></span>

<span data-ttu-id="03e77-116">, `QuantumSimulator` Gereken doğrusal algeköşeli paralel hale getirmek Için [OpenMP](http://www.openmp.org/) kullanır.</span><span class="sxs-lookup"><span data-stu-id="03e77-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="03e77-117">Varsayılan olarak, OpenMP kullanılabilir olan tüm donanım iş parçacıklarını kullanır. Böylelikle, gereken koordinasyon asıl işi küçülteceği için az sayıda qubit’i olan programlar sıkça yavaş çalışır.</span><span class="sxs-lookup"><span data-stu-id="03e77-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="03e77-118">Bu, ortam değişkeni `OMP_NUM_THREADS` küçük bir sayı olarak ayarlanarak düzeltilebilir.</span><span class="sxs-lookup"><span data-stu-id="03e77-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="03e77-119">Üstünkörü bir temel kural olarak, 1 iş parçacığı yaklaşık 4 qubit için uygundur ve her qubit başına bir tane ek iş parçacığı iyi bir sonuç verir. Ancak, bu kullandığınız algoritmaya yüksek oranda bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="03e77-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

