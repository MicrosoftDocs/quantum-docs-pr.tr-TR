---
title: Kuantum Katalarına giriş
description: Microsoft Quantum Development Kit (QDK) tarafından sağlanan katalar (eğitim alıştırmaları) hakkında bilgi edinin
author: bradben
ms.author: bradben
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 1c4dfa5c47aa38935cd5936cd256e357b6605371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276221"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Kuantum Kataları ile kuantum bilişimini öğrenin

[Hisse katas](https://github.com/Microsoft/QuantumKatas/) , aynı anda hisse bilgi Işlem ve Q # programlama öğelerine eğitim eden açık kaynaklı, kendi kendine adımlı öğreticiler ve programlama alıştırmaları içerir.

## <a name="learning-by-doing"></a>Yaparak öğrenme

Bu projede bir araya getirilmiş olan öğreticiler ve alıştırmalar, çok basitten başlayarak artan zorluk derecelerine sahip olan belirli konu başlıklarını içeren programlama görevleri sayesinde yaparak öğrenmenin önemini vurgulamaktadır. Her görev biraz kod yazmanızı gerektirir; ilk görevler tek satır kod gerektirirken sonraki görevlerde oldukça büyük bir kod parçası gerekebilir.

En önemlisi, katas, görevler için çözümler kuran, çalıştıran ve doğrulayan test çerçevelerini içerir. Bu sayede anında çözümünüzle ilgili geri bildirim alabilir ve hatalı yaklaşımlarınızı düzeltebilirsiniz.

Eğitim için katas 'yi tercih ettiğiniz ortamınızda kullanabilirsiniz:

* Binder ortamında çevrimiçi Jupyter Notebook'lar
* Yerel makinenizde çalışan Jupyter Notebook'lar
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Kuantum Katalarıyla ne öğrenebilirim?

Hisse bilgi işlem ve temel bilgilerin temellerini ve temellerini inceleyin. Kuantum bilişiminin temel kavramlarını iyi bir şekilde anladığınızdan emin olmak için başlangıçta bu öğrenme yolunu izlemenizi öneririz. Tabii ki dilerseniz kompleks aritmetik gibi bilgi sahibi olduğunuz konuları atlayabilir, algoritmaları istediğiniz sırada öğrenebilirsiniz.

### <a name="introduction-to-quantum-computing-concepts"></a>Kuantum bilişimi kavramlarına giriş

| Ta | Description |
|:-----|-------------|
|[Kompleks aritmetik](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)|Bu öğreticide, sanal ve karmaşık sayılar gibi hisse kullanımı için gerekli olan matematiksel arka planın bazıları açıklanmaktadır.|
|[Doğrusal cebir](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)|Doğrusal algedeniz, hisse ve ABD bilgi işlem işlemlerini temsil etmek için kullanılır. Bu öğretici, matrisler ve vektörler dahil olmak üzere temel bilgileri içerir.|
|[Kubit kavramı](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/Qubit)|Hisse bitlerinin temel kavramlarından biri olan qubits hakkında bilgi edinin. |
|[Tek kubitli kuantum geçitleri](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates)|Bu öğretici, hisse algoritmalarının yapı taşları olarak davranan ve hisse qubit durumlarını çeşitli yollarla dönüştüren tek qubit hisse geçitlerini tanıtır.|
|[Çoklu kubit sistemleri](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitSystems)|Bu öğretici, Multi-qubit sistemlerini, matematiksel gösterimde ve Q # kodundaki gösterimi ve entanglement kavramını tanıtır.|
|[Multi-qubit hisse geçitleri](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitGates)|Bu öğretici, [tek qubit hisse kapıları](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates) öğreticisini izler ve Multi-qubit sistemlerine hisse kugeçitleri uygulamaya odaklanır.|

### <a name="quantum-computing-fundamentals"></a>Kuantum bilişimi ile ilgili temel bilgiler

| Ta | Description |
|:-----|-------------|
|[Kuantum geçitlerini tanıma](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)|Q # içindeki temel hisse geçitlerini tanımanız için tasarlanan bir dizi alıştırmada. Temel tek qubit ve Multi-qubit kapıları, adjoint ve kontrollü kapıları ve bir qubit durumunu değiştirmek için kapıları nasıl kullanacağınızı içerir.|
|[Kuantum süper konumu oluşturma](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)|Soru-cevap kavramı ve Q # içinde programlama kavramı hakkında bilgi almak için bu alıştırmaları kullanın. Temel tek qubit ve Multi-qubit kapıları, superposition ve Flow denetimi ve Q # içinde özyineleme için alıştırmaları içerir.|
|[Ölçümleri kullanarak kuantum durumlarını ayırt etme](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)|Bu alýþtýrmalarý, hisse ölçümü ve dikgen olmayan durumlar hakkında bilgi alırken çözün. |
|[Birleşik ölçümler](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)|Birleşik eşlik ölçümleri hakkında bilgi edinin ve [ölçüm](xref:microsoft.quantum.intrinsic.measure) işleminin hisse bilgilerini ayırt etmek için nasıl kullanılacağını öğrenin.|

### <a name="algorithms"></a>Algoritmalar

| Ta | Description |
|:-----|-------------|
|[Kuantum ışınlanması](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)|Bu küta, yalnızca klasik iletişim ve daha önce paylaşılan hisse kullanımı ile daha önce paylaşılan hisse|
|[Süper yoğun kodlama](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)|Yoğun kodlama, daha önce paylaşılan hisse kullanımı ' nı kullanarak yalnızca bir qubit göndererek, iki bitlik klasik bilgi aktarımına izin veren bir protokoldür.  |
|[Deutsch–Jozsa algoritması](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringDeutschJozsaAlgorithm)|Bu algoritma, herhangi bir belirleyici algoritmadan daha hızlı üstel bir hisse algoritması örneklerinden biri olmak üzere çok büyük.|
|[Grover arama algoritmasının üst düzey özelliklerini keşfetme](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringGroversAlgorithm)|Hisse hesaplamalarındaki en yoğun algoritmalardan birine yönelik yüksek düzey bir giriş. Belirli bir çıktıyı üreten bir siyah kutuya (Oracle) giriş bulma sorununu çözer. |
|[Grover arama algoritmasını uygulama](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)|Bu kür, Grover 'in arama algoritmasında daha ayrıntılı bir hale gelir ve Oracles yazmayı, algoritmaların adımlarını gerçekleştirmeyi ve son olarak bir araya getirme işlemini içerir.|
|[Grover 'in algoritmasını kullanarak gerçek sorunları çözme: SAT sorunları](https://github.com/microsoft/QuantumKatas/tree/master/SolveSATWithGrover)|Örnek olarak [Boolean tatfilebilirlik sorunları](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) (Sat) kullanarak gerçekçi sorunları çözümlemek Için Grover 'in algoritmasını kullanan bir dizi alıştırmada.  |
|[Grover 'in algoritmasını kullanarak gerçek sorunları çözme: grafik renklendirme sorunları](https://github.com/microsoft/QuantumKatas/tree/master/GraphColoring)| Bu küta, bir örnek olarak bir grafik renklendirme sorununu çözmek için Grover 'in algoritmasını, bu kez [kısıtlama memnuniyeti sorunlarını](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem)çözmenize yardımcı olacak şekilde araştırır. |

### <a name="protocols-and-libraries"></a>Protokoller ve kitaplıklar

| Ta | Description |
|:-----|-------------|
|[Kuantum anahtar dağıtımı için BB84 protokolü](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)|Şifreleme anahtarlarını değiştirmek için qubit kullanarak [BB84](https://en.wikipedia.org/wiki/BB84)ve bir hisse |
|[Bit-çevir hata düzeltme kodu](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)|En basit hisse hata düzeltme (QEC) kodlarıyla birlikte hisse hata düzeltmesini keşfet-üç-qubit bit-çevir kodu.|
|[Aşama tahmini](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)|Aşama tahmini algoritmaları, hisse bilgi işlem 'nin en temel yapı taşlarından bazılarıdır. Hisse alma aşaması tahmini olan bu alýþtýrmalar ve Q # ' da aşama tahmini yordamlarını hazırlama ve çalıştırma hakkında bilgi edinin.|
|[Hisse aritmetiğini: Ripple-taşıma Ekleyici oluşturma](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)|Bir hisse bilgisayar üzerinde [Ripple](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder) 'ın eklenmesini sağlayan, derinlemesine bir grup dizi. Yerinde hisse Adder oluşturun, bunu farklı bir algoritmayla genişletin ve son olarak, yerinde bir hisse kaşık oluşturun.   |

### <a name="entanglement-games"></a>Dolaşıklık oyunları

| Ta | Description |
|:-----|-------------|
|[CHSH oyunu](https://github.com/microsoft/QuantumKatas/tree/master/CHSHGame)|[Chsh](https://en.wikipedia.org/wiki/CHSH_inequality) oyununun bir uygulamasıyla hisse zenginl. Bu [Yerel](https://en.wikipedia.org/wiki/Quantum_refereed_game) olmayan oyun, tam olarak klasik bir stratejiyle ne kadar olabildiğini öğrenmek için hisse uygun bir şekilde nasıl kullanılabileceğini gösterir.|
|[GHZ oyunu](https://github.com/microsoft/QuantumKatas/tree/master/GHZGame)|GHZ oyunu başka bir yerel olmayan oyundur, ancak üç oyuncu içerir.|
|[Mermin-Peres sihirli kare oyunu](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)|Bir sihirli kare oyunu çözümlemek için [hisse sahte-Telepathy](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game) 'yi denetleyen bir dizi alıştırmada.  |

## <a name="resources"></a>Kaynaklar

[Kuantum Kataları](https://github.com/microsoft/QuantumKatas)'nın tam serisine bakın

[Kataları çevrimiçi çalıştırın](https://aka.ms/try-quantum-katas)
