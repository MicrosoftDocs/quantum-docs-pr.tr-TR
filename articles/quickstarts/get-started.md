---
uid: microsoft.quantum.welcome
title: Quantum Development Kit'i (QDK) kullanmaya başlama
description: Microsoft Quantum geliştirme setiyle Q# dilinde kuantum projelerini programlamaya nasıl başlayacağınızı öğrenin.
author: bradben
ms.author: bradben
ms.date: 5/10/2020
ms.topic: overview
ms.openlocfilehash: ff4a3dc829423525e18d89d5ed3d621079d1a524
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274198"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a><span data-ttu-id="89e2b-103">Quantum Development Kit'i (QDK) kullanmaya başlama</span><span class="sxs-lookup"><span data-stu-id="89e2b-103">Get started with the Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="89e2b-104">Microsoft Quantum Development Kit'e hoş geldiniz!</span><span class="sxs-lookup"><span data-stu-id="89e2b-104">Welcome to the Microsoft Quantum Development Kit!</span></span>  

<span data-ttu-id="89e2b-105">Quantum geliştirme seti (QDK), özellikle kuantum uygulamaları geliştirmek için tasarlanan bir programlama dili olan Q# ile kendi kuantum programlarınızı ve denemelerinizi oluşturmak için ihtiyacınız olan tüm araçları içerir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-105">The Quantum Development Kit (QDK) contains all the tools you'll need to build your own quantum programs and experiments with Q#, a programming language designed specifically for quantum application development.</span></span>

<span data-ttu-id="89e2b-106">[QDK yükleme kılavuzu](xref:microsoft.quantum.install) ile hemen başlayın.</span><span class="sxs-lookup"><span data-stu-id="89e2b-106">To jump right in, start with the [QDK installation guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="89e2b-107">Bu kılavuzda, kendi kuantum programlarınızı yazabilmeniz için Quantum geliştirme setini Windows, Linux veya MacOS makinelere yükleme rehberliği alacaksınız.</span><span class="sxs-lookup"><span data-stu-id="89e2b-107">You'll be guided through installing the Quantum Development Kit on Windows, Linux, or MacOS machines so that you can write your own quantum programs.</span></span>

<span data-ttu-id="89e2b-108">Kuantum bilişimi konusunda yeniyseniz, kuantum bilgisayarların neler yapabileceğini ve kuantum bilişimi ile ilgili temel bilgileri öğrenmek için [Genel bakış](xref:microsoft.quantum.overview.introduction) bölümünü gözden geçirin.</span><span class="sxs-lookup"><span data-stu-id="89e2b-108">If you're new to quantum computing, review the [Overview](xref:microsoft.quantum.overview.introduction) section to learn what quantum computers can do and the fundamentals of quantum computing.</span></span>

## <a name="get-started-programming"></a><span data-ttu-id="89e2b-109">Programlamaya başlayın</span><span class="sxs-lookup"><span data-stu-id="89e2b-109">Get started programming</span></span>

<span data-ttu-id="89e2b-110">Quantum Geliştirme Seti, Q# ile kuantum programı geliştirmeyi öğrenmek için birçok yol sunar.</span><span class="sxs-lookup"><span data-stu-id="89e2b-110">The Quantum Development Kit provides many ways to learn how to develop a quantum program with Q#.</span></span>
<span data-ttu-id="89e2b-111">Kuantumun gücünden yararlanmaya başlamak için öğreticilerimizi deneyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="89e2b-111">To get up and running with the power of quantum, you can try out our tutorials:</span></span>

* <span data-ttu-id="89e2b-112">[Kuantum rastgele sayı oluşturucusu](xref:microsoft.quantum.quickstarts.qrng): Kuantum kavramlarına yönelik kısa bir tanıtım sağlarken aynı zamanda birkaç dakika içinde bir kuantum uygulaması oluşturup çalıştırmanıza olanak tanıyan "Q# Merhaba Dünya" stilinde bir uygulama ile başlayın.</span><span class="sxs-lookup"><span data-stu-id="89e2b-112">[Quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) - Start with a "Q# Hello World" style application, providing a brief introduction to quantum concepts while letting you build and run a quantum application in minutes.</span></span>
* <span data-ttu-id="89e2b-113">[Q# ile dolaşıklığı keşfetme](xref:microsoft.quantum.write-program): Bu öğretici, kuantum programlamanın bazı temel kavramlarını gösteren bir Q# programı yazma adımlarında size rehberlik eder.</span><span class="sxs-lookup"><span data-stu-id="89e2b-113">[Explore entanglement with Q#](xref:microsoft.quantum.write-program) - This tutorial guides you on writing a Q# program that demonstrates some of the foundational concepts of quantum programming.</span></span>
    <span data-ttu-id="89e2b-114">Kodlamaya başlamaya hazır değilseniz, yine de QDK'yi yüklemeden anlatımı takip ederek Q# bilgisayar diline genel bir bakış elde edebilir ve kuantum bilişiminin ilk kavramlarını öğrenebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89e2b-114">If you are not ready to start coding, you can still follow along without installing the QDK and get an overview of the Q# programming language and the first concepts of quantum computing.</span></span>
* <span data-ttu-id="89e2b-115">[Grover arama algoritması](xref:microsoft.quantum.quickstarts.search): Kuantum algoritmasına alt düzey kuantum işlemlerini soyutlama açısından yaklaşan ve Q# dilinin gücü hakkında fikir edinmenizi sağlayan bu Q# programı örneğini keşfedin.</span><span class="sxs-lookup"><span data-stu-id="89e2b-115">[Grover’s search algorithm](xref:microsoft.quantum.quickstarts.search) - Explore this example of a Q# program to get an idea of the power of Q# for expressing the quantum algorithm in a way that abstracts the low-level quantum operations.</span></span>
    <span data-ttu-id="89e2b-116">Bu öğretici, Visual Studio veya Visual Studio Code kullanarak programı bir Q# komut satırı uygulaması olarak geliştirme sürecinde size rehberlik eder.</span><span class="sxs-lookup"><span data-stu-id="89e2b-116">This tutorial guides you through developing the program as a Q# command line application, using Visual Studio or Visual Studio Code.</span></span>

### <a name="learning-further"></a><span data-ttu-id="89e2b-117">Daha fazlasını öğrenme</span><span class="sxs-lookup"><span data-stu-id="89e2b-117">Learning further</span></span>
* <span data-ttu-id="89e2b-118">[Kuantum bilişimi için Microsoft Learn modülleri](https://docs.microsoft.com/learn/browse/?term=quantum), temel kavramlar konusunda size uygun hızda ve zamanda ustalaşmayı öğretir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-118">The [Microsoft Learn modules for quantum computing](https://docs.microsoft.com/learn/browse/?term=quantum) will teach you to master core concepts at your speed and on your schedule.</span></span> <span data-ttu-id="89e2b-119">[İlk modülümüzü](https://docs.microsoft.com/learn/modules/qsharp-create-first-quantum-development-kit/) kullanarak QDK ile kuantum programlarının nasıl oluşturulacağı ile ilgili temel bilgileri öğrenebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89e2b-119">You can learn the basics of how to create quantum programs with the QDK with our [first module](https://docs.microsoft.com/learn/modules/qsharp-create-first-quantum-development-kit/).</span></span>
* <span data-ttu-id="89e2b-120">Q# programlama hakkında daha ayrıntılı bilgi edinmek istiyorsanız, Q# içinde programlama alıştırmaları aracılığıyla kuantum bilişimini tanıtan ve kendi hızınızda ilerleyebileceğiniz bir alıştırma koleksiyonu olan [Quantum Katas](https://github.com/Microsoft/QuantumKatas)’a göz atın.</span><span class="sxs-lookup"><span data-stu-id="89e2b-120">If you want to dive deeper into Q# programming, check out the [Quantum Katas](https://github.com/Microsoft/QuantumKatas) - a collection of self-paced programming exercises that introduce you to quantum computing via programming exercises in Q#.</span></span>
    <span data-ttu-id="89e2b-121">Bu kata’ların çoğu ayrıca Q# Not Defterleri olarak da sunulur.</span><span class="sxs-lookup"><span data-stu-id="89e2b-121">Many of these katas are also available as Q# Notebooks.</span></span> 
* <span data-ttu-id="89e2b-122">[Örnek depomuzda](https://github.com/Microsoft/Quantum), Q# kullanarak kuantum programları yazmaya yönelik çok sayıda örnek bulunur.</span><span class="sxs-lookup"><span data-stu-id="89e2b-122">Our [samples repository](https://github.com/Microsoft/Quantum) showcases multiple examples on how to write quantum programs using Q#.</span></span> <span data-ttu-id="89e2b-123">Bu örneklerin çoğu, [standart](xref:microsoft.quantum.libraries.standard.intro) ve [kimya](xref:microsoft.quantum.chemistry.concepts.intro) kitaplıkları dahil açık kaynak [kuantum kitaplıklarımız](https://github.com/Microsoft/QuantumLibraries) kullanılarak yazılmıştır. (Aşağıda bu konu hakkında daha fazla bilgi bulabilirsiniz.)</span><span class="sxs-lookup"><span data-stu-id="89e2b-123">Most of these samples are written using our open-source [quantum libraries](https://github.com/Microsoft/QuantumLibraries), including our [standard](xref:microsoft.quantum.libraries.standard.intro) and [chemistry](xref:microsoft.quantum.chemistry.concepts.intro) libraries (more info on these below).</span></span>

## <a name="key-concepts-for-quantum-computing"></a><span data-ttu-id="89e2b-124">Kuantum bilişimine yönelik temel kavramlar</span><span class="sxs-lookup"><span data-stu-id="89e2b-124">Key concepts for quantum computing</span></span>

<span data-ttu-id="89e2b-125">Kuantum geliştirmeye yeni başladıysanız tüm bunların biraz kafa karıştırıcı olabileceğinin farkındayız.</span><span class="sxs-lookup"><span data-stu-id="89e2b-125">If you are a newcomer to quantum development, we know that this can all seem a bit daunting.</span></span> <span data-ttu-id="89e2b-126">Bu temel kavramlar, kuantum dünyasına adım atmanıza ve kuantum bilişiminin hangi bakımlardan klasik bilişimden farklı olduğunu anlamanıza yardımcı olmak için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="89e2b-126">These key concepts are designed to help you step into the quantum world and understand how quantum computing differs from classical computing.</span></span>

* [<span data-ttu-id="89e2b-127">Kuantum bilişimini anlama</span><span class="sxs-lookup"><span data-stu-id="89e2b-127">Understanding quantum computing</span></span>](xref:microsoft.quantum.overview.understanding)
* [<span data-ttu-id="89e2b-128">Kuantum bilgisayarlar ve kuantum simülatörleri</span><span class="sxs-lookup"><span data-stu-id="89e2b-128">Quantum computers and quantum simulators</span></span>](xref:microsoft.quantum.overview.simulators)
* [<span data-ttu-id="89e2b-129">Q# programlama dili ve QDK nedir?</span><span class="sxs-lookup"><span data-stu-id="89e2b-129">What are the Q# programming language and the QDK?</span></span>](xref:microsoft.quantum.overview.q-sharp)
* [<span data-ttu-id="89e2b-130">Kuantum bilişimi için doğrusal cebir</span><span class="sxs-lookup"><span data-stu-id="89e2b-130">Linear algebra for quantum computing</span></span>](xref:microsoft.quantum.overview.algebra)

## <a name="quantum-development-kit-documentation"></a><span data-ttu-id="89e2b-131">Quantum Geliştirme Seti Belgeleri</span><span class="sxs-lookup"><span data-stu-id="89e2b-131">Quantum Development Kit Documentation</span></span>

<span data-ttu-id="89e2b-132">Geçerli belge aşağıdaki ek konuları içerir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-132">The current documentation includes the following additional topics.</span></span>

### <a name="q-developer-guides"></a><span data-ttu-id="89e2b-133">Q# geliştirici kılavuzları</span><span class="sxs-lookup"><span data-stu-id="89e2b-133">Q# developer guides</span></span>

* <span data-ttu-id="89e2b-134">[Q# Kullanıcı Kılavuzu](xref:microsoft.quantum.guide), Q# dilinde kuantum programları oluşturmak için kullanılan temel kavramları ayrıntılı olarak açıklar.</span><span class="sxs-lookup"><span data-stu-id="89e2b-134">[Q# User Guide](xref:microsoft.quantum.guide) details the core concepts used to create quantum programs in Q#.</span></span>
* <span data-ttu-id="89e2b-135">[Kuantum simülatörleri ve konak uygulamaları](xref:microsoft.quantum.machines), kuantum algoritmalarının yürütülme şeklini, hangi kuantum makinelerinin kullanılabilir olduğunu ve kuantum programı için Q# dışı bir sürücü yazmayı açıklar.</span><span class="sxs-lookup"><span data-stu-id="89e2b-135">[Quantum simulators and host applications](xref:microsoft.quantum.machines) describes how quantum algorithms are executed, what quantum machines are available, and how to write a non-Q# driver for the quantum program.</span></span>

### <a name="q-libraries"></a><span data-ttu-id="89e2b-136">Q# kitaplıkları</span><span class="sxs-lookup"><span data-stu-id="89e2b-136">Q# libraries</span></span>

* <span data-ttu-id="89e2b-137">[Q# standart kitaplıkları](xref:microsoft.quantum.libraries.standard.intro), hem klasik dil denetimi gereksinimini hem de Q# kuantum algoritmasını destekleyen işlemleri ve işlevleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="89e2b-137">[Q# standard libraries](xref:microsoft.quantum.libraries.standard.intro) describes the operations and functions that support both the classical language control requirement and the Q# quantum algorithms.</span></span> 
    <span data-ttu-id="89e2b-138">Denetim akışı, veri yapıları, hata düzeltme, test ve hata ayıklama konularını içerir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-138">Topics include control flow, data structures, error correction, testing, and debugging.</span></span> 
* <span data-ttu-id="89e2b-139">[Q# kimya kitaplığı](xref:microsoft.quantum.chemistry.concepts.intro), kuantum bilişiminin kritik bir uygulaması olan kuantum kimya simülasyonunu destekleyen işlemleri ve işlevleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="89e2b-139">[Q# chemistry library](xref:microsoft.quantum.chemistry.concepts.intro) describes the operations and functions that support quantum chemistry simulation---a critical application of quantum computing.</span></span> <span data-ttu-id="89e2b-140">Hamiltonian dinamiği simülasyonu, kuantum aşama tahmini ve diğer konuları içerir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-140">Topics include simulating Hamiltonian dynamics and quantum phase estimation, among others.</span></span>
* <span data-ttu-id="89e2b-141">[Q# nümerik kitaplığı](xref:microsoft.quantum.numerics.intro), hedef makinelerin yerel işlemleri açısından karmaşık aritmetik işlevleri ifade etmeyi destekleyen işlemleri ve işlevleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="89e2b-141">[Q# numerics library](xref:microsoft.quantum.numerics.intro) describes the operations and functions that support expressing complicated arithmetic functions in terms of the native operations of target machines.</span></span>
* <span data-ttu-id="89e2b-142">[Q# kitaplık başvurusu](xref:microsoft.quantum.standardlibsintro), ad alanına göre kitaplık varlıkları hakkında başvuru bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-142">[Q# library reference](xref:microsoft.quantum.standardlibsintro) contains reference information about library entities by namespace.</span></span>

### <a name="general-quantum-computing"></a><span data-ttu-id="89e2b-143">Genel kuantum bilişimi</span><span class="sxs-lookup"><span data-stu-id="89e2b-143">General quantum computing</span></span>

* <span data-ttu-id="89e2b-144">[Kuantum bilişimi kavramları](xref:microsoft.quantum.concepts.intro), doğrusal cebirin kuantum bilişimindeki yeri, qubit’lerin doğası ve kullanımı, kuantum bağlantı hattını okuma ve diğer konuları içerir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-144">[Quantum computing concepts](xref:microsoft.quantum.concepts.intro) includes topics such as the relevance of linear algebra to quantum computing, the nature and use of a qubit, how to read a quantum circuit, and more.</span></span>
* <span data-ttu-id="89e2b-145">[Kuantum bilişimi sözlüğü](xref:microsoft.quantum.glossary), kuantum bilişimine ve program geliştirmeye özgü bazı önemli terimleri içeren bir sözlüktür.</span><span class="sxs-lookup"><span data-stu-id="89e2b-145">[Quantum computing glossary](xref:microsoft.quantum.glossary) is a glossary of some crucial terms specific to quantum computing and program development.</span></span>
    <span data-ttu-id="89e2b-146">Bu alanda yeniyseniz, belgelerimizi okurken bu sözlük kullanışlı bir başvuru olabilir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-146">If you are new to the field, this could be a handy reference as you read through our documentation.</span></span>
* <span data-ttu-id="89e2b-147">[Daha fazla bilgi](xref:microsoft.quantum.more-information), kuantum bilişimi konularının ayrıntılı olarak incelenmesi için özel olarak seçilen başvuruları içerir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-147">[Further reading](xref:microsoft.quantum.more-information) contains specially selected references for in-depth coverage of quantum computing topics.</span></span>

### <a name="additional-info"></a><span data-ttu-id="89e2b-148">Ek bilgiler</span><span class="sxs-lookup"><span data-stu-id="89e2b-148">Additional info</span></span>

* <span data-ttu-id="89e2b-149">[Microsoft Quantum Geliştirme Seti sürüm notları](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="89e2b-149">[Microsoft Quantum Development kit release notes](xref:microsoft.quantum.relnotes).</span></span>


## <a name="be-a-part-of-the-q-open-source-community"></a><span data-ttu-id="89e2b-150">Q# Açık Kaynak Topluluğu’nun bir parçası olun</span><span class="sxs-lookup"><span data-stu-id="89e2b-150">Be a part of the Q# Open-Source Community</span></span>

<span data-ttu-id="89e2b-151">Quantum Geliştirme Seti, dünyanın en önemli sorunlarını çözebilmemiz için geliştiricilerin kuantum bilişimini herkes için daha erişilebilir yapmasına yardımcı olan bir açık kaynak geliştirme setidir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-151">The Quantum Development Kit is an open-source development kit that empowers developers to make quantum computing more accessible to all so that we can solve some of the world's most pressing challenges.</span></span>  <span data-ttu-id="89e2b-152">Açık kaynak yazılım gerektiren akademik kurumlar, kendi kuantum öğrenme ve geliştirme çalışmaları için Q#’ı dağıtabilir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-152">Academic institutions who require open-source software will be able to deploy Q# for their quantum learning and development.</span></span> <span data-ttu-id="89e2b-153">Geliştirme setinin açık kaynak olması ayrıca geliştiricilere ve etki alanı uzmanlarına, kodları aracılığıyla iyileştirme ve fikir katkısında bulunma fırsatı sunar.</span><span class="sxs-lookup"><span data-stu-id="89e2b-153">Open-sourcing the development kit also empowers developers and domain experts an opportunity to contribute improvements and ideas via their code.</span></span>

<span data-ttu-id="89e2b-154">Quantum Geliştirme Seti’ne yönelik geri bildiriminiz, katılımınız ve katkılarınız önemlidir.</span><span class="sxs-lookup"><span data-stu-id="89e2b-154">Your feedback, participation and contributions to the Quantum Development Kit is important.</span></span>  <span data-ttu-id="89e2b-155">Quantum Geliştirme Seti kaynakları hakkında daha fazla bilgi edinmek, geri bildirim sağlamak, kararlara nasıl katılabileceğinizi ve büyüyen bu kuantum geliştirme platformuna nasıl katkıda bulunabileceğinizi öğrenmek için bkz. [Quantum Geliştirme Seti’ne katkı yapma](xref:microsoft.quantum.contributing).</span><span class="sxs-lookup"><span data-stu-id="89e2b-155">To learn more about the Quantum Development Kit sources, provide feedback, and find out how you can participate in the decisions and contribute to this growing quantum development platform, see [Contributing to the Quantum Development Kit](xref:microsoft.quantum.contributing).</span></span>

<span data-ttu-id="89e2b-156">Microsoft’un kuantum bilişimi girişimi hakkında daha fazla genel bilgi almak istiyorsanız bkz. [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).</span><span class="sxs-lookup"><span data-stu-id="89e2b-156">If you'd like more general information about Microsoft's quantum computing initiative, see [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).</span></span>