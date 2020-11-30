---
title: Q# Kullanıcı Kılavuzu
description: Kullanıcı Kılavuzunun amacına ve içeriğine yönelik genel bakış
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231766"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="88409-103">Q# Kullanıcı Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="88409-103">The Q# User Guide</span></span>

<span data-ttu-id="88409-104">Q# Kullanıcı Kılavuzu’na hoş geldiniz!</span><span class="sxs-lookup"><span data-stu-id="88409-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="88409-105">Bu kılavuzdaki farklı konularda, Q# kullanarak kuantum programları geliştirmeye yönelik bazı temel bilgiler sunulmaktadır.</span><span class="sxs-lookup"><span data-stu-id="88409-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="88409-106">Q# kuantum bilgisayar diline yönelik tam belirtim ve belgeler için [Q# dil kılavuzuna](xref:microsoft.quantum.qsharp.index) başvuracağız.</span><span class="sxs-lookup"><span data-stu-id="88409-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="88409-107">Kullanıcı Kılavuzu İçeriği</span><span class="sxs-lookup"><span data-stu-id="88409-107">User Guide Contents</span></span>

- <span data-ttu-id="88409-108">[Q# programları](xref:microsoft.quantum.guide.programs): Q# içinde kuantum programlarına hızlı bir giriş.</span><span class="sxs-lookup"><span data-stu-id="88409-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="88409-109">[Q# programı çalıştırmanın yolları](xref:microsoft.quantum.guide.host-programs): Q# programının nasıl çalıştırılacağını açıklar ve programı çağırabileceğiniz çeşitli yöntemlere ilişkin bir genel bakış sunar. Komut satırından, Q# Jupyter Not Defterleri içinde veya Python ya da bir .NET dilinde yazılmış klasik konak programından çalıştırma seçenekleri bu yöntemler arasındadır.</span><span class="sxs-lookup"><span data-stu-id="88409-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="88409-110">[Test etme ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging): Kodunuzun istendiği şekilde çalıştığından emin olmaya yönelik bazı teknikleri ayrıntılarıyla açıklar.</span><span class="sxs-lookup"><span data-stu-id="88409-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="88409-111">Kuantum bilgilerinin genel opaklığı nedeniyle, bir kuantum programında hata ayıklamak için özel teknikler gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="88409-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="88409-112">Neyse ki, Q# kuantuma özgü tekniklerin yanı sıra programcıların tanıdığı klasik hata ayıklama tekniklerinin birçoğunu destekler.</span><span class="sxs-lookup"><span data-stu-id="88409-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="88409-113">Bunlar Q# dilinde birim testi oluşturmayı ve çalıştırmayı, kodunuzda değerlere ve olasılıklara *onay* eklemeyi ve hedef makine durumunun çıkışını oluşturan `Dump` işlevlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="88409-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="88409-114">Sonuncusu, bazı kuantum sınırlamalarını (örneğin, [kopyalamama teoremi](xref:microsoft.quantum.concepts.pauli)) atlayarak hesaplamaların belirli bölümlerinde hata ayıklamak için tam durumlu simülatörümüzle birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="88409-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="88409-115">Kuantum Simülatörleri ve Kaynak Tahmin Araçları</span><span class="sxs-lookup"><span data-stu-id="88409-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="88409-116">[Kuantum simülatörleri ve konak uygulamaları](xref:microsoft.quantum.machines): Kullanılabilen farklı simülatörlerin yanı sıra, konak programların ve hedef makinelerin birlikte çalışarak Q# programlarını nasıl çalıştırdığına yönelik bir genel bakış.</span><span class="sxs-lookup"><span data-stu-id="88409-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="88409-117">[Tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator): Tam kuantum durumunun simülasyonunu yapan hedef makine.</span><span class="sxs-lookup"><span data-stu-id="88409-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="88409-118">Daha küçük ölçekli programları (birkaç düzine kubitten küçük) tamamen çalıştırmak veya bunlarda hata ayıklamak için faydalıdır</span><span class="sxs-lookup"><span data-stu-id="88409-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="88409-119">[Kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator): Bir kuantum bilgisayarda Q# işleminin belirli bir örneğini çalıştırmak için gereken kaynaklara yönelik tahmin yapar.</span><span class="sxs-lookup"><span data-stu-id="88409-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="88409-120">[İzleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Kuantum bilgisayar durumunun simülasyonunu yapmadan bir kuantum programı çalıştırır ve böylece binlerce kubit kullanan kuantum programlarını da çalıştırabilir.</span><span class="sxs-lookup"><span data-stu-id="88409-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="88409-121">Bir kuantum programındaki klasik kodda hata ayıklamak ve gerekli kaynakları tahmin etmek için yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="88409-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="88409-122">[Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator): Milyonlarca kubitle kullanılabilen özel amaçlı bir kuantum simülatörü. Yalnızca kısıtlanmış kuantum işlemleri kümesi içeren programlar içindir (örneğin X, CNOT ve çok denetimli X).</span><span class="sxs-lookup"><span data-stu-id="88409-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="88409-123">Hızlı Başvuru Sayfaları</span><span class="sxs-lookup"><span data-stu-id="88409-123">Quick Reference Pages</span></span>

- <span data-ttu-id="88409-124">[IQ# Magic Komutları](xref:microsoft.quantum.guide.quickref.iqsharp): Q# Jupyter Not Defterlerindeki IQ# magic komutlarına yönelik hızlı başvuru sayfası.</span><span class="sxs-lookup"><span data-stu-id="88409-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
