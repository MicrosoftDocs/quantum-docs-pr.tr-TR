---
title: Q# Kullanıcı Kılavuzu
description: Kullanıcı Kılavuzunun amacına ve içeriğine yönelik genel bakış
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430620"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="2c19f-103">Q# Kullanıcı Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="2c19f-103">The Q# User Guide</span></span>

<span data-ttu-id="2c19f-104">Q# Kullanıcı Kılavuzu’na hoş geldiniz!</span><span class="sxs-lookup"><span data-stu-id="2c19f-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="2c19f-105">Burada Q# diline ait temel kavramların ve kuantum programları yazmak için ihtiyaç duyduğunuz bilgilerin ayrıntılarını paylaşıyoruz.</span><span class="sxs-lookup"><span data-stu-id="2c19f-105">Here we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="2c19f-106">Kullanıcı Kılavuzu İçeriği</span><span class="sxs-lookup"><span data-stu-id="2c19f-106">User Guide Contents</span></span>

- <span data-ttu-id="2c19f-107">[Q# Hakkındaki Temel Bilgiler](xref:microsoft.quantum.guide.basics): Q# programlama dilinin amacı ve işlevlerine yönelik genel bir bakış.</span><span class="sxs-lookup"><span data-stu-id="2c19f-107">[Q# Basics](xref:microsoft.quantum.guide.basics): an introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="2c19f-108">Q# Dili</span><span class="sxs-lookup"><span data-stu-id="2c19f-108">Q# Language</span></span>

- <span data-ttu-id="2c19f-109">[Q# Dilindeki Türler](xref:microsoft.quantum.guide.types): Q# tür modelini yerleştirir ve türleri belirtip bunlarla çalışmaya yönelik söz dizimini açıklar.</span><span class="sxs-lookup"><span data-stu-id="2c19f-109">[Types in Q#](xref:microsoft.quantum.guide.types): lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="2c19f-110">[Tür İfadeleri](xref:microsoft.quantum.guide.expressions): Q# dilindeki her türe ait değeri belirtme, birleştirme ve bu değere başvurup değer üzerinde çalışma ayrıntıları.</span><span class="sxs-lookup"><span data-stu-id="2c19f-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="2c19f-111">Q# kullanma</span><span class="sxs-lookup"><span data-stu-id="2c19f-111">Using Q#</span></span>

- <span data-ttu-id="2c19f-112">[Q# Dosya Yapısı](xref:microsoft.quantum.guide.filestructure): `*.qs` Q# dosyasının yapısını ve söz dizimini açıklar.</span><span class="sxs-lookup"><span data-stu-id="2c19f-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="2c19f-113">[İşlemler ve İşlevler](xref:microsoft.quantum.guide.operationsfunctions): Q# dilinin çağrılabilir iki türü hakkında ayrıntılar sağlar: *işlemler*, kubit kayıt defterleri üzerindeki eylemleri içerir ve *işlevler*, yalnızca klasik bilgilerle çalışır.</span><span class="sxs-lookup"><span data-stu-id="2c19f-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): details the two callable types of the Q# language: *operations*, which include action on qubit registers and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="2c19f-114">Burada, kuantum işlemlerinin eklenik ve denetlenmiş sürümleri dahil olmak üzere bunları nasıl tanımlayıp çağıracağınızı göreceksiniz.</span><span class="sxs-lookup"><span data-stu-id="2c19f-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="2c19f-115">[Değişkenler](xref:microsoft.quantum.guide.variables): Q# programlarındaki değişkenlerin rolünü ve bunların nasıl etkili bir şekilde kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="2c19f-115">[Variables](xref:microsoft.quantum.guide.variables): describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="2c19f-116">Örneğin, bağlama kapsamlarının yanı sıra, sabit/değişebilen değişkenler arasındaki farklar ve bunları atayıp atamalarını kaldırma hakkında bilgiler bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2c19f-116">For example, you can find information about binding scopes, as well as the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="2c19f-117">[Kubitlerle çalışma](xref:microsoft.quantum.guide.qubits): Tek başına kubitlere ve kubit sistemlerine yönelik olarak kullanılan Q# özelliklerini açıklar.</span><span class="sxs-lookup"><span data-stu-id="2c19f-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): describes the features of Q# used to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="2c19f-118">Özellikle, bunların ayrılmasını, bunlara yönelik işlemler gerçekleştirmeyi ve son olarak ölçülerini kapsar.</span><span class="sxs-lookup"><span data-stu-id="2c19f-118">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 

- <span data-ttu-id="2c19f-119">[Denetim Akışı](xref:microsoft.quantum.guide.controlflow): Çok sayıda standart tekniğin (koşullu yürütme, for döngüleri, while döngüleri vb.) yanı sıra kuantuma özgü “Başarılı Olana Kadar Yinele” desenini de içeren, Q# dilindeki programlama denetim akışı desenlerinin ayrıntılarını içerir.</span><span class="sxs-lookup"><span data-stu-id="2c19f-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): details the programming control flow patterns available in Q#, which includes many standard techniques (conditional execution, for loops, while loops, etc.) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="2c19f-120">[Test ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging): Kodunuzun doğru şekilde çalıştığından emin olmaya yönelik bazı teknikleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="2c19f-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="2c19f-121">Kuantum bilgilerinin genel opaklığı nedeniyle, bir kuantum programında hata ayıklamak için özel teknikler gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="2c19f-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="2c19f-122">Neyse ki, Q# kuantuma özgü tekniklerin yanı sıra klasik hata ayıklama tekniklerinin birçoğunu destekler.</span><span class="sxs-lookup"><span data-stu-id="2c19f-122">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="2c19f-123">Bunlar Q# içinde birim testi oluşturmayı/çalıştırmayı, kodunuzda değerlere ve olasılıklara *onay deyimi* eklemeyi ve hedef makine durumunun çıkışını oluşturan `Dump` işlevlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="2c19f-123">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="2c19f-124">Sonuncusu, bazı kuantum sınırlamalarını (ör. kopyalamama teoremi) atlayarak işlemlerin belirli bölümlerinde hata ayıklamak için tam durum simülatörümüzle birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="2c19f-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="2c19f-125">Kuantum Simülatörleri ve Kaynak Tahmin Araçları</span><span class="sxs-lookup"><span data-stu-id="2c19f-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="2c19f-126">[Kuantum simülatörleri ve konak uygulamaları](xref:microsoft.quantum.machines): Kullanılabilen farklı simülatörlerin yanı sıra, konak program ve hedef makineler arasındaki genel yürütme modeline yönelik bir genel bakış.</span><span class="sxs-lookup"><span data-stu-id="2c19f-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): an overview of the different simulators available, as well as the general execution model between host program and target machines.</span></span>

- <span data-ttu-id="2c19f-127">[Tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator): Tam kuantum durumunu simüle eden hedef makine.</span><span class="sxs-lookup"><span data-stu-id="2c19f-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): the target machine which simulates the full quantum state.</span></span> <span data-ttu-id="2c19f-128">Daha küçük ölçekli programları (birkaç düzine kubitten küçük) tamamen yürütme veya bunlarda hata ayıklamada kullanılır</span><span class="sxs-lookup"><span data-stu-id="2c19f-128">Useful for fully executing or debugging smaller scale programs (less than a couple dozen qubits)</span></span>

- <span data-ttu-id="2c19f-129">[Kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator): Bir kuantum bilgisayarda Q# işleminin belirli bir örneğini çalıştırmak için gereken kaynaklara yönelik tahmin yapar.</span><span class="sxs-lookup"><span data-stu-id="2c19f-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="2c19f-130">[İzleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro): kuantum bilgisayarın durumunu gerçekten taklit etmeden bir kuantum programı yürütür ve böylece binlerce kubit kullanan kuantum programlarını da yürütülebilir.</span><span class="sxs-lookup"><span data-stu-id="2c19f-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="2c19f-131">Bir kuantum programındaki klasik kodda hata ayıklamak ve gerekli kaynakları tahmin etmek için yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="2c19f-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="2c19f-132">[Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator): Milyonlarca kubitle kullanılabilen özel amaçlı bir kuantum simülatörü. Yalnızca kısıtlanmış kuantum işlemleri kümesi içeren programlar içindir (örneğin X, CNOT ve çok denetimli X).</span><span class="sxs-lookup"><span data-stu-id="2c19f-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): a special purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations (namely X, CNOT, and multi-controlled X).</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="2c19f-133">Hızlı Başvuru Sayfaları</span><span class="sxs-lookup"><span data-stu-id="2c19f-133">Quick Reference Pages</span></span>

- <span data-ttu-id="2c19f-134">[IQ# Magic Komutları](xref:microsoft.quantum.guide.quickref.iqsharp): Q# Jupyter Notebook’lardaki IQ# magic komutlarına yönelik hızlı başvuru sayfası.</span><span class="sxs-lookup"><span data-stu-id="2c19f-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
