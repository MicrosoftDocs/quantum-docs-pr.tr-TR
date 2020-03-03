---
title: Kuantum kimyası örnek uygulamaları
description: Microsoft Quantum kimya kitaplığının örnek uygulamalarını keşfedin.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906500"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="27163-103">Kuantum kimyası örnekleri</span><span class="sxs-lookup"><span data-stu-id="27163-103">Quantum chemistry examples</span></span>

<span data-ttu-id="27163-104">Kuantum kimyası kavramlarında, el ile örnek fermion Hamiltonian’ları oluşturduk.</span><span class="sxs-lookup"><span data-stu-id="27163-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="27163-105">Artık, [Hamiltonian dinamiklerinin simülasyonunu yapma](xref:microsoft.quantum.libraries.standard.algorithms) bölümünde özetlenen kimya simülasyonu algoritmalarını canon kitaplığındaki [kuantum aşaması tahmini](xref:microsoft.quantum.libraries.characterization) ile birleştiriyoruz.</span><span class="sxs-lookup"><span data-stu-id="27163-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="27163-106">Bu birleşim, temsil edilen moleküldeki enerji düzeylerine yönelik tahmin elde etmemize olanak tanır. Bu, bir kuantum bilgisayardaki kuantum kimyasının önemli uygulamalarından biridir.</span><span class="sxs-lookup"><span data-stu-id="27163-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="27163-107">Hamiltonian’ın koşullarını tek tek belirtmek yerine, ölçeğe uygun kimya denemeleri gerçekleştirmemize olanak tanıyan bazı örneklerle de çalışırız.</span><span class="sxs-lookup"><span data-stu-id="27163-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="27163-108">Hamiltonian’ın [Broombridge şemasında](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) kodladığı bir kimyayı yükleyerek başlayacağız.</span><span class="sxs-lookup"><span data-stu-id="27163-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="27163-109">Simülasyonu [Tam durumlu simülatörde](xref:microsoft.quantum.machines.full-state-simulator) yapılamayacak kadar büyük olan moleküllerde ilgi çekici bilimler hala gerçekleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="27163-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="27163-110">Örneğin, büyük kimya simülasyonu gerçekleştirmeye yönelik kaynak maliyetleri [izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) hedeflenerek değerlendirilebilir.</span><span class="sxs-lookup"><span data-stu-id="27163-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="27163-111">Şimdi, sağlanan örneklerin bazıları ile kimya simülasyonu kitaplığının ilgi çekici uygulamalarını göstereceğiz.</span><span class="sxs-lookup"><span data-stu-id="27163-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>
