---
title: Hisse geliştirme seti Toffoli simülatör
description: Milyonlarca qubitle kullanılabilecek özel bir amaç simülatörü olan Microsoft QDK Toffoli benzeticileri hakkında bilgi edinin.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276026"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="dbd06-103">Hisse geliştirme seti Toffoli simülatör</span><span class="sxs-lookup"><span data-stu-id="dbd06-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="dbd06-104">Hisse geliştirme seti, X, CNOT ve çok kontrollü X hisse malarıyla (tüm klasik mantık ve hesaplamalar kullanılabilir) sınırlı olan hisse cıcılarının benzetimini yapan bir Toffoli simülasyonu sağlar.</span><span class="sxs-lookup"><span data-stu-id="dbd06-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="dbd06-105">Toffoli simülatör, [tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator)tarafından çok daha kısıtlanıyor olsa da, bu çok daha fazla qubit benzetimi yapabilir.</span><span class="sxs-lookup"><span data-stu-id="dbd06-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="dbd06-106">Toffoli simülatörü milyonlarca qubitle birlikte kullanılabilir, ancak tam durum simülatörü genellikle yaklaşık 30 ' a sınırlanır.</span><span class="sxs-lookup"><span data-stu-id="dbd06-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="dbd06-107">Bilgisayarınızda Q # dilinde yazılmış sınırlı bir hisse algoritması kümesini yürütebilir ve hata ayıklaması yapabilir; Örneğin, Boole işlevlerini değerlendiren Oracles bu kapıları kullanılarak uygulanabilir ve bu nedenle test, bu simülatörü kullanan büyük sayıda qubit farklılık gösterir.</span><span class="sxs-lookup"><span data-stu-id="dbd06-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="dbd06-108">Bu hisse Benzetici, sınıfı aracılığıyla sunulur `ToffoliSimulator` .</span><span class="sxs-lookup"><span data-stu-id="dbd06-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="dbd06-109">Simülatörü kullanmak için, bu sınıfın bir örneğini oluşturun ve `Run` diğer parametrelerin geri kalanında birlikte yürütmek istediğiniz hisse işlem yöntemine geçirin:</span><span class="sxs-lookup"><span data-stu-id="dbd06-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="dbd06-110">Diğer Işlemler</span><span class="sxs-lookup"><span data-stu-id="dbd06-110">Other Operations</span></span>

<span data-ttu-id="dbd06-111">, `ToffoliSimulator` Ve gibi, `R` `Exp` ortaya çıkan işlem, `X` kimliğe veya kimliğe eşit olduğunda, ve gibi dağıtılmış Paulis 'leri destekler.</span><span class="sxs-lookup"><span data-stu-id="dbd06-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="dbd06-112">Ölçüm ve onaylama desteklenir, ancak yalnızca Pauli `Z` temelinde desteklenir.</span><span class="sxs-lookup"><span data-stu-id="dbd06-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="dbd06-113">Bazı ölçüm olasılığının her zaman 0 veya 1 olduğunu unutmayın; Toffoli benzeticisinde rastgele bir değer yoktur.</span><span class="sxs-lookup"><span data-stu-id="dbd06-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="dbd06-114">`DumpMachine`ve `DumpRegister` desteklenir.</span><span class="sxs-lookup"><span data-stu-id="dbd06-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="dbd06-115">Her ikisi de `Z` her bir qubit, satır başına bir qubit olmak üzere her bir qubit için geçerli olan durum</span><span class="sxs-lookup"><span data-stu-id="dbd06-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="dbd06-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="dbd06-116">QubitCount</span></span>

<span data-ttu-id="dbd06-117">Varsayılan olarak, `ToffoliSimulator` 65.536 qubit için alan ayırır.</span><span class="sxs-lookup"><span data-stu-id="dbd06-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="dbd06-118">Algoritmanız bundan fazla gerektiriyorsa, oluşturucuya parametre için bir değer sağlayarak qubit sayısını değiştirebilirsiniz `qubitCount` .</span><span class="sxs-lookup"><span data-stu-id="dbd06-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="dbd06-119">Her ek qubit ek bir bellek gerektirir, bu nedenle ihtiyaç duyacağınız qubit sayısını fazla tahmin etmek için önemli bir maliyet yoktur.</span><span class="sxs-lookup"><span data-stu-id="dbd06-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="dbd06-120">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="dbd06-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
