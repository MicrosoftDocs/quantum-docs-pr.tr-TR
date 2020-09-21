---
title: Kuantum Katalarına giriş
description: Microsoft Quantum Development Kit (QDK) tarafından sağlanan katalar (eğitim alıştırmaları) hakkında bilgi edinin
author: bradben
ms.author: v-benbra
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
no-loc:
- Q#
- $$v
ms.openlocfilehash: 097d7f70088b6ee84a1e91ee99be59149dd9e15b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834831"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Kuantum Kataları ile kuantum bilişimini öğrenin

[Hisse katas](https://github.com/Microsoft/QuantumKatas/) , her zaman bilgi işlem ve programlama öğelerine aynı anda eğitim eden açık kaynaklı, kendi kendine adımlı öğreticiler ve programlama alıştırmaları içerir Q# .

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

| Ta | Açıklama |
|:-----|-------------|
|[Kompleks aritmetik](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ComplexArithmetic)|Bu öğreticide, sanal ve karmaşık sayılar gibi hisse kullanımı için gerekli olan matematiksel arka planın bazıları açıklanmaktadır.|
|[Doğrusal cebir](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/LinearAlgebra)|Doğrusal algedeniz, hisse ve ABD bilgi işlem işlemlerini temsil etmek için kullanılır. Bu öğretici, matrisler ve vektörler dahil olmak üzere temel bilgileri içerir.|
|[Kubit kavramı](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/Qubit)|Hisse bitlerinin temel kavramlarından biri olan qubits hakkında bilgi edinin. |
|[Tek kubitli kuantum geçitleri](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/SingleQubitGates)|Bu öğretici, hisse algoritmalarının yapı taşları olarak davranan ve hisse qubit durumlarını çeşitli yollarla dönüştüren tek qubit hisse geçitlerini tanıtır.|
|[Çoklu kubit sistemleri](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/MultiQubitSystems)|Bu öğretici, Multi-qubit sistemlerini, matematiksel gösterimde ve kod içinde gösterimini Q# ve entanglement kavramını tanıtır.|
|[Multi-qubit hisse geçitleri](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/MultiQubitGates)|Bu öğretici, [tek qubit hisse kapıları](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/SingleQubitGates) öğreticisini izler ve Multi-qubit sistemlerine hisse kugeçitleri uygulamaya odaklanır.|

### <a name="quantum-computing-fundamentals"></a>Kuantum bilişimi ile ilgili temel bilgiler

| Ta | Açıklama |
|:-----|-------------|
|[Kuantum geçitlerini tanıma](https://github.com/microsoft/QuantumKatas/tree/main/BasicGates)|İçindeki temel hisse geçitlerini tanımanız için tasarlanan bir dizi alıştırmada Q# . Temel tek qubit ve Multi-qubit kapıları, adjoint ve kontrollü kapıları ve bir qubit durumunu değiştirmek için kapıları nasıl kullanacağınızı içerir.|
|[Kuantum süper konumu oluşturma](https://github.com/microsoft/QuantumKatas/tree/main/Superposition)|' De üst konum ve programlama kavramı hakkında bilgi sahibi olmak için bu alýþtýrmalarý kullanın Q# . Temel tek qubit ve Multi-qubit kapıları, superposition ve Flow denetimi ve özyineleme için alıştırmaları içerir Q# .|
|[Ölçümleri kullanarak kuantum durumlarını ayırt etme](https://github.com/microsoft/QuantumKatas/tree/main/Measurements)|Bu alýþtýrmalarý, hisse ölçümü ve dikgen olmayan durumlar hakkında bilgi alırken çözün. |
|[Birleşik ölçümler](https://github.com/microsoft/QuantumKatas/tree/main/JointMeasurements)|Birleşik eşlik ölçümleri hakkında bilgi edinin ve [ölçüm](xref:microsoft.quantum.intrinsic.measure) işleminin hisse bilgilerini ayırt etmek için nasıl kullanılacağını öğrenin.|

### <a name="algorithms"></a>Algoritmalar

| Ta | Açıklama |
|:-----|-------------|
|[Kuantum ışınlanması](https://github.com/microsoft/QuantumKatas/tree/main/Teleportation)|Bu küta, yalnızca klasik iletişim ve daha önce paylaşılan hisse kullanımı ile daha önce paylaşılan hisse|
|[Süper yoğun kodlama](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding)|Yoğun kodlama, daha önce paylaşılan hisse kullanımı ' nı kullanarak yalnızca bir qubit göndererek, iki bitlik klasik bilgi aktarımına izin veren bir protokoldür.  |
|[Deutsch–Jozsa algoritması](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ExploringDeutschJozsaAlgorithm)|Bu algoritma, herhangi bir belirleyici algoritmadan daha hızlı üstel bir hisse algoritması örneklerinden biri olmak üzere çok büyük.|
|[Grover arama algoritmasının üst düzey özelliklerini keşfetme](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ExploringGroversAlgorithm)|Hisse hesaplamalarındaki en yoğun algoritmalardan birine yönelik yüksek düzey bir giriş. Belirli bir çıktıyı üreten bir siyah kutuya (Oracle) giriş bulma sorununu çözer. |
|[Grover arama algoritmasını uygulama](https://github.com/microsoft/QuantumKatas/tree/main/GroversAlgorithm)|Bu kür, Grover 'in arama algoritmasında daha ayrıntılı bir hale gelir ve Oracles yazmayı, algoritmaların adımlarını gerçekleştirmeyi ve son olarak bir araya getirme işlemini içerir.|
|[Grover 'in algoritmasını kullanarak gerçek sorunları çözme: SAT sorunları](https://github.com/microsoft/QuantumKatas/tree/main/SolveSATWithGrover)|Örnek olarak [Boolean tatfilebilirlik sorunları](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) (Sat) kullanarak gerçekçi sorunları çözümlemek Için Grover 'in algoritmasını kullanan bir dizi alıştırmada.  |
|[Grover 'in algoritmasını kullanarak gerçek sorunları çözme: grafik renklendirme sorunları](https://github.com/microsoft/QuantumKatas/tree/main/GraphColoring)| Bu küta, bir örnek olarak bir grafik renklendirme sorununu çözmek için Grover 'in algoritmasını, bu kez [kısıtlama memnuniyeti sorunlarını](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem)çözmenize yardımcı olacak şekilde araştırır. |

### <a name="protocols-and-libraries"></a>Protokoller ve kitaplıklar

| Ta | Açıklama |
|:-----|-------------|
|[Kuantum anahtar dağıtımı için BB84 protokolü](https://github.com/microsoft/QuantumKatas/tree/main/KeyDistribution_BB84)|Şifreleme anahtarlarını değiştirmek için qubit kullanarak [BB84](https://en.wikipedia.org/wiki/BB84)ve bir hisse |
|[Bit-çevir hata düzeltme kodu](https://github.com/microsoft/QuantumKatas/tree/main/QEC_BitFlipCode)|En basit hisse hata düzeltme (QEC) kodlarıyla birlikte hisse hata düzeltmesini keşfet-üç-qubit bit-çevir kodu.|
|[Aşama tahmini](https://github.com/microsoft/QuantumKatas/blob/main/PhaseEstimation)|Aşama tahmini algoritmaları, hisse bilgi işlem 'nin en temel yapı taşlarından bazılarıdır. Hisse aşamalı tahmini ve ' de aşama tahmini yordamlarını hazırlama ve çalıştırma konusundaki bu alýþtýrmalar ile aşama tahmini hakkında bilgi edinin Q# .|
|[Hisse aritmetiğini: Ripple-taşıma Ekleyici oluşturma](https://github.com/microsoft/QuantumKatas/blob/main/RippleCarryAdder)|Bir hisse bilgisayar üzerinde [Ripple](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder) 'ın eklenmesini sağlayan, derinlemesine bir grup dizi. Yerinde hisse Adder oluşturun, bunu farklı bir algoritmayla genişletin ve son olarak, yerinde bir hisse kaşık oluşturun.   |

### <a name="entanglement-games"></a>Dolaşıklık oyunları

| Ta | Açıklama |
|:-----|-------------|
|[CHSH oyunu](https://github.com/microsoft/QuantumKatas/tree/main/CHSHGame)|[Chsh](https://en.wikipedia.org/wiki/CHSH_inequality) oyununun bir uygulamasıyla hisse zenginl. Bu [Yerel](https://en.wikipedia.org/wiki/Quantum_refereed_game) olmayan oyun, tam olarak klasik bir stratejiyle ne kadar olabildiğini öğrenmek için hisse uygun bir şekilde nasıl kullanılabileceğini gösterir.|
|[GHZ oyunu](https://github.com/microsoft/QuantumKatas/tree/main/GHZGame)|GHZ oyunu başka bir yerel olmayan oyundur, ancak üç oyuncu içerir.|
|[Mermin-Peres sihirli kare oyunu](https://github.com/microsoft/QuantumKatas/tree/main/MagicSquareGame)|Bir sihirli kare oyunu çözümlemek için [hisse sahte-Telepathy](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game) 'yi denetleyen bir dizi alıştırmada.  |

## <a name="resources"></a>Kaynaklar

[Kuantum Kataları](https://github.com/microsoft/QuantumKatas)'nın tam serisine bakın

[Kataları çevrimiçi çalıştırın](https://aka.ms/try-quantum-katas)
