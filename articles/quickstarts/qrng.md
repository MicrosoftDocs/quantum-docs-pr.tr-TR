---
title: Kuantum Rastgele Sayı Oluşturucusu Oluşturma
description: Kuantum rastgele sayı oluşturucusu tasarlayarak süper konum gibi temel kuantum kavramlarını gösteren bir Q# projesi oluşturun.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: c3039b92c4b3235a397d5cf31280ac2673706e9d
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462844"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="53af9-103">Hızlı Başlangıç: Q# ile Kuantum Rastgele Sayı Oluşturucusu Oluşturma Tasarlama</span><span class="sxs-lookup"><span data-stu-id="53af9-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="53af9-104">Kuantum rastgele sayı oluşturucusu, Q# dilinde yazılmış kuantum algoritmalarına örnek olarak gösterilebilir.</span><span class="sxs-lookup"><span data-stu-id="53af9-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="53af9-105">Bu algoritma, kuantum mekaniklerinin özelliklerinden faydalanarak rastgele bir sayı üretir.</span><span class="sxs-lookup"><span data-stu-id="53af9-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="53af9-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="53af9-106">Prerequisites</span></span>

- <span data-ttu-id="53af9-107">Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="53af9-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="53af9-108">Q# projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="53af9-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="53af9-109">Q# işlemi yazma</span><span class="sxs-lookup"><span data-stu-id="53af9-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="53af9-110">Q# işlem kodu</span><span class="sxs-lookup"><span data-stu-id="53af9-110">Q# operation code</span></span>

1. <span data-ttu-id="53af9-111">Operation.qs dosyasının içeriğini aşağıdaki kodla değiştirin:</span><span class="sxs-lookup"><span data-stu-id="53af9-111">Replace the contents of the Operation.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

<span data-ttu-id="53af9-112">[Kuantum Bilişimi nedir?](xref:microsoft.quantum.overview.what) makalesinde de belirttiğimiz gibi kubit, süper konumda olabilen bir kuantum bilgi birimidir.</span><span class="sxs-lookup"><span data-stu-id="53af9-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="53af9-113">Bir kubit ölçüldüğünde yalnızca 0 veya 1 olabilir.</span><span class="sxs-lookup"><span data-stu-id="53af9-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="53af9-114">Ancak yürütme sırasında kubitin durumu bir ölçümle 0 veya 1 değerini elde etme olasılığını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="53af9-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="53af9-115">Olasılığa dayalı olan bu durum, süper konum olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="53af9-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="53af9-116">Bu olasılığı kullanarak rastgele sayı oluşturabiliriz.</span><span class="sxs-lookup"><span data-stu-id="53af9-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="53af9-117">Q# işlemimizde yerel bir Q# veri türü olan `Qubit` veri türünü kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="53af9-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="53af9-118">`Qubit` ayırmak için `using` deyimi kullanmamız gerekir.</span><span class="sxs-lookup"><span data-stu-id="53af9-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="53af9-119">Ayrılan kubit her zaman `Zero` durumunda olur.</span><span class="sxs-lookup"><span data-stu-id="53af9-119">When it gets allocated a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="53af9-120">`H` işlemini kullanarak, `Qubit` öğemizi süper konuma alabiliriz.</span><span class="sxs-lookup"><span data-stu-id="53af9-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="53af9-121">Kubiti ölçmek ve değerini okumak için `M` iç işlemi kullanılır.</span><span class="sxs-lookup"><span data-stu-id="53af9-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="53af9-122">`Qubit` öğemizi üst konuma alıp ölçtüğümüzde elde ettiğimiz sonuç, kod her çağrıldığında farklı bir değer verecektir.</span><span class="sxs-lookup"><span data-stu-id="53af9-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="53af9-123">`Qubit` serbest bırakıldığında açıkça `Zero` durumuna geri alınmalıdır, aksi halde simülatörde çalışma zamanı hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="53af9-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="53af9-124">Bunu yapmanın kolay yollarından biri `Reset` çağırmaktır.</span><span class="sxs-lookup"><span data-stu-id="53af9-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="53af9-125">Bloch küresi ile kodu görselleştirme</span><span class="sxs-lookup"><span data-stu-id="53af9-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="53af9-126">Bloch küresinde kuzey kutbu klasik **0** değerini, güney kutbu ise klasik **1** değerini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="53af9-126">In the Bloch sphere the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="53af9-127">Süper konum, küredeki bir nokta ile gösterilebilir (ok simgesi kullanılır).</span><span class="sxs-lookup"><span data-stu-id="53af9-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="53af9-128">Okun ucu kutba ne kadar akın olursa kubitin ölçüm sonrasında o kutba atanmış olan klasik değeri alma ihtimali o kadar yüksek olur.</span><span class="sxs-lookup"><span data-stu-id="53af9-128">When the closer the end of the arrow to a pole, the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="53af9-129">Örneğin aşağıda kırmızı ok ile gösterilen kubit durumunun ölçüldüğünde **0** değerini verme olasılığı yüksektir.</span><span class="sxs-lookup"><span data-stu-id="53af9-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="./Bloch.svg" width="175">

<span data-ttu-id="53af9-130">Kodun gerçekleştirdiği işlemleri görselleştirmek için şu gösterimi kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="53af9-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="53af9-131">İlk olarak **0** durumunda başlatılan bir kubitle başlıyoruz ve **0** ile **1** olasılıklarının aynı olduğu bir süper konum oluşturmak için buna `H` uyguluyoruz.</span><span class="sxs-lookup"><span data-stu-id="53af9-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="./H.svg" width="450">

* <span data-ttu-id="53af9-132">Ardından kubiti ölçüp çıktıyı kaydediyoruz:</span><span class="sxs-lookup"><span data-stu-id="53af9-132">Then we measure the qubit and save the output:</span></span>

<img src="./Measurement2.svg" width="450">

<span data-ttu-id="53af9-133">Ölçümün sonucu tamamen rastgele olduğundan rastgele bir bit elde ettik.</span><span class="sxs-lookup"><span data-stu-id="53af9-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="53af9-134">Bu işlemi birkaç kere çağırarak farklı tamsayılar oluşturabiliriz.</span><span class="sxs-lookup"><span data-stu-id="53af9-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="53af9-135">Örneğin üç rastgele bit elde etmek için işlemi üç kez çağırarak rastgele 3 bitlik sayılar (0 ile 7 arasında rastgele bir sayı) oluşturabiliriz.</span><span class="sxs-lookup"><span data-stu-id="53af9-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>
