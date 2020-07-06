---
title: Q# Kullanıcı Kılavuzu
description: Kullanıcı Kılavuzunun amacına ve içeriğine yönelik genel bakış
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: 078d86c808b26c7f0b7b2577020cd9cef9491a9d
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885009"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="fb969-103">Q# Kullanıcı Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="fb969-103">The Q# User Guide</span></span>

<span data-ttu-id="fb969-104">Q# Kullanıcı Kılavuzu’na hoş geldiniz!</span><span class="sxs-lookup"><span data-stu-id="fb969-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="fb969-105">Bu kılavuzun farklı konularında, Q# diline ait temel kavramların ve kuantum programları yazmak için ihtiyaç duyduğunuz bilgilerin ayrıntılarını paylaşıyoruz.</span><span class="sxs-lookup"><span data-stu-id="fb969-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="fb969-106">Kullanıcı Kılavuzu İçeriği</span><span class="sxs-lookup"><span data-stu-id="fb969-106">User Guide Contents</span></span>

- <span data-ttu-id="fb969-107">[Q# Temel Bilgileri](xref:microsoft.quantum.guide.basics): Q# programlama dilinin amacı ve işlevselliğine yönelik tanıtıcı bir genel bakış.</span><span class="sxs-lookup"><span data-stu-id="fb969-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

- <span data-ttu-id="fb969-108">[Q# programını çalıştırma yolları](xref:microsoft.quantum.guide.host-programs): Q# programının nasıl yürütüleceğini açıklar ve şunlar gibi programı çağırabileceğiniz çeşitli yöntemlere genel bir bakış sunar: komut satırından, Q# Jupyter Notebook içinde veya Python ya da .NET dilinde yazılmış bir klasik konak programından.</span><span class="sxs-lookup"><span data-stu-id="fb969-108">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is executed, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

### <a name="q-language"></a><span data-ttu-id="fb969-109">Q# Dili</span><span class="sxs-lookup"><span data-stu-id="fb969-109">Q# Language</span></span>

- <span data-ttu-id="fb969-110">[Q# Dilindeki Türler](xref:microsoft.quantum.guide.types): Q# tür modeline açıklık getirir ve türleri belirtip bunlarla çalışmaya yönelik söz dizimini açıklar.</span><span class="sxs-lookup"><span data-stu-id="fb969-110">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="fb969-111">[Tür İfadeleri](xref:microsoft.quantum.guide.expressions): Q# dilindeki her türden değerleri belirtme, birleştirme ve bu değere başvurup üzerlerinde çalışmayı ayrıntılarıyla açıklar.</span><span class="sxs-lookup"><span data-stu-id="fb969-111">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="fb969-112">Q# kullanma</span><span class="sxs-lookup"><span data-stu-id="fb969-112">Using Q#</span></span>

- <span data-ttu-id="fb969-113">[Q# Dosya Yapısı](xref:microsoft.quantum.guide.filestructure): `*.qs` Q# dosyasının yapısını ve söz dizimini açıklar.</span><span class="sxs-lookup"><span data-stu-id="fb969-113">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="fb969-114">[İşlemler ve İşlevler](xref:microsoft.quantum.guide.operationsfunctions): Q# dilinin çağrılabilir iki türü hakkında ayrıntılar sağlar: *işlemler*, kubit yazmaçları üzerindeki eylemleri içerir ve *işlevler*, yalnızca klasik bilgilerle çalışır.</span><span class="sxs-lookup"><span data-stu-id="fb969-114">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="fb969-115">Burada, kuantum işlemlerinin eklenik ve denetlenmiş sürümleri dahil olmak üzere bunları nasıl tanımlayıp çağıracağınızı göreceksiniz.</span><span class="sxs-lookup"><span data-stu-id="fb969-115">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="fb969-116">[Değişkenler](xref:microsoft.quantum.guide.variables): Q# programlarındaki değişkenlerin rolünü ve bunların nasıl etkili bir şekilde kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="fb969-116">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="fb969-117">Örneğin, bağlama kapsamlarının yanı sıra, sabit ve değişebilen değişkenler arasındaki fark ve bunları atayıp atamalarını kaldırma hakkında bilgiler bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fb969-117">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="fb969-118">[Kubitlerle çalışma](xref:microsoft.quantum.guide.qubits): Tek tek kubitleri ve kubit sistemlerini adreslemek için kullanılan Q# özelliklerini, özellikle bunları ayırmayı, bunlar üzerinde işlem gerçekleştirmeyi ve bunları ölçmeyi açıklar.</span><span class="sxs-lookup"><span data-stu-id="fb969-118">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="fb969-119">[Denetim Akışı](xref:microsoft.quantum.guide.controlflow): Çok sayıda standart tekniğin (koşullu yürütme, for döngüleri, while döngüleri gibi) yanı sıra kuantuma özgü “Başarılı Olana Kadar Yinele” desenini de içeren, Q# dilindeki kullanılabilir programlama denetim akışı desenlerini ayrıntılarıyla açıklar.</span><span class="sxs-lookup"><span data-stu-id="fb969-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional execution, for loops, while loops) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="fb969-120">[Test etme ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging): Kodunuzun istendiği şekilde çalıştığından emin olmaya yönelik bazı teknikleri ayrıntılarıyla açıklar.</span><span class="sxs-lookup"><span data-stu-id="fb969-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="fb969-121">Kuantum bilgilerinin genel opaklığı nedeniyle, bir kuantum programında hata ayıklamak için özel teknikler gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="fb969-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="fb969-122">Neyse ki, Q# kuantuma özgü tekniklerin yanı sıra programcıların tanıdığı klasik hata ayıklama tekniklerinin birçoğunu destekler.</span><span class="sxs-lookup"><span data-stu-id="fb969-122">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="fb969-123">Bunlar Q# içinde birim testi oluşturmayı ve çalıştırmayı, kodunuzda değerlere ve olasılıklara *onay* eklemeyi ve hedef makine durumunun çıkışını oluşturan `Dump` işlevlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="fb969-123">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="fb969-124">Sonuncusu, bazı kuantum sınırlamalarını (örneğin, [kopyalamama teoremi](xref:microsoft.quantum.concepts.pauli)) atlayarak hesaplamaların belirli bölümlerinde hata ayıklamak için tam durumlu simülatörümüzle birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="fb969-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="fb969-125">Kuantum Simülatörleri ve Kaynak Tahmin Araçları</span><span class="sxs-lookup"><span data-stu-id="fb969-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="fb969-126">[Kuantum simülatörleri ve konak uygulamaları](xref:microsoft.quantum.machines): Kullanılabilir farklı simülatörlerin yanı sıra, konak programlar ve hedef makineler arasındaki genel yürütme modeline yönelik bir genel bakış.</span><span class="sxs-lookup"><span data-stu-id="fb969-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well as the general execution model between host programs and target machines.</span></span>

- <span data-ttu-id="fb969-127">[Tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator): Tam kuantum durumunun simülasyonunu yapan hedef makine.</span><span class="sxs-lookup"><span data-stu-id="fb969-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="fb969-128">Daha küçük ölçekli programları (birkaç düzine kubitten küçük) tamamen yürütmek veya bunlarda hata ayıklamak için faydalıdır</span><span class="sxs-lookup"><span data-stu-id="fb969-128">Useful for fully executing or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="fb969-129">[Kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator): Bir kuantum bilgisayarda Q# işleminin belirli bir örneğini çalıştırmak için gereken kaynaklara yönelik tahmin yapar.</span><span class="sxs-lookup"><span data-stu-id="fb969-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="fb969-130">[İzleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Kuantum bilgisayar durumunun simülasyonunu yapmadan bir kuantum programı yürütür ve böylece binlerce kubit kullanan kuantum programlarını da yürütülebilir.</span><span class="sxs-lookup"><span data-stu-id="fb969-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="fb969-131">Bir kuantum programındaki klasik kodda hata ayıklamak ve gerekli kaynakları tahmin etmek için yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="fb969-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="fb969-132">[Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator): Milyonlarca kubitle kullanılabilen özel amaçlı bir kuantum simülatörü. Yalnızca kısıtlanmış kuantum işlemleri kümesi içeren programlar içindir (örneğin X, CNOT ve çok denetimli X).</span><span class="sxs-lookup"><span data-stu-id="fb969-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="fb969-133">Hızlı Başvuru Sayfaları</span><span class="sxs-lookup"><span data-stu-id="fb969-133">Quick Reference Pages</span></span>

- <span data-ttu-id="fb969-134">[IQ# Magic Komutları](xref:microsoft.quantum.guide.quickref.iqsharp): Q# Jupyter Notebook’lardaki IQ# magic komutlarına yönelik hızlı başvuru sayfası.</span><span class="sxs-lookup"><span data-stu-id="fb969-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
