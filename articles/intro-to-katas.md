---
title: Kuantum Katalarına giriş
description: Microsoft Quantum Development Kit (QDK) tarafından sağlanan katalar (eğitim alıştırmaları) hakkında bilgi edinin
author: natke
ms.author: nakersha
ms.date: 10/17/2019
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 204033c81b1f6d05c255170ee5662ce9388c3dbf
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660742"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Kuantum Kataları ile kuantum bilişimini öğrenin

[Kuantum Kataları](https://github.com/Microsoft/QuantumKatas/), size aynı anda hem kuantum bilişiminin hem de Q# programlamanın öğelerini öğretmeyi amaçlayan, kendi hızınızda ilerleyebileceğiniz açık kaynak öğreticilerden ve programlama alıştırmalarından oluşan bir koleksiyonudur.

## <a name="learning-by-doing"></a>Yaparak öğrenme

Bu projede bir araya getirilmiş olan öğreticiler ve alıştırmalar, çok basitten başlayarak artan zorluk derecelerine sahip olan belirli konu başlıklarını içeren programlama görevleri sayesinde yaparak öğrenmenin önemini vurgulamaktadır. Her görev biraz kod yazmanızı gerektirir; ilk görevler tek satır kod gerektirirken sonraki görevlerde oldukça büyük bir kod parçası gerekebilir.

En önemlisi de katalar, görev çözümlerini oluşturan, çalıştıran ve doğrulayan test çerçevelerine sahiptir. Bu sayede anında çözümünüzle ilgili geri bildirim alabilir ve hatalı yaklaşımlarınızı düzeltebilirsiniz.

Kataları kullanarak kuantum bilişimi tercih ettiğiniz ortamda öğrenebilirsiniz:

* Binder ortamında çevrimiçi Jupyter Notebook'lar
* Yerel makinenizde çalışan Jupyter Notebook'lar
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Kuantum Katalarıyla ne öğrenebilirim?

Kuantum Katalarında yer verilen ana konu başlıkları aşağıda özet halinde verilmiştir. Kuantum bilişiminin temel kavramlarını iyi bir şekilde anladığınızdan emin olmak için başlangıçta bu öğrenme yolunu izlemenizi öneririz. Tabii ki dilerseniz kompleks aritmetik gibi bilgi sahibi olduğunuz konuları atlayabilir, algoritmaları istediğiniz sırada öğrenebilirsiniz.

### <a name="introduction-to-quantum-computing-concepts"></a>Kuantum bilişimi kavramlarına giriş

* [Kompleks aritmetik](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)
* [Doğrusal cebir](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)
* [Kubit kavramı](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/Qubit)
* [Tek kubitli kuantum geçitleri](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates)
* [Çoklu kubit sistemleri](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitSystems)
* [Çoklu kubit geçitleri](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitGates)

### <a name="quantum-computing-fundamentals"></a>Kuantum bilişimi ile ilgili temel bilgiler

* [Kuantum geçitlerini tanıma](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)
* [Kuantum süper konumu oluşturma](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)
* [Ölçümleri kullanarak kuantum durumlarını ayırt etme](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)
* [Birleşik ölçümler](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)

### <a name="algorithms"></a>Algoritmalar

* [Kuantum ışınlanması](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)
* [Süper yoğun kodlama](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)
* [Deutsch–Jozsa algoritması](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringDeutschJozsaAlgorithm)
* [Grover arama algoritmasını uygulama](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)
* [Grover arama algoritmasının üst düzey özelliklerini keşfetme](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringGroversAlgorithm)
* Grover algoritmasını kullanarak gerçek sorunları çözme: [SAT problemleri](https://github.com/microsoft/QuantumKatas/tree/master/SolveSATWithGrover) ve [graf renklendirme problemleri](https://github.com/microsoft/QuantumKatas/tree/master/GraphColoring)

### <a name="protocols-and-libraries"></a>Protokoller ve kitaplıklar

* [Kuantum anahtar dağıtımı için BB84 protokolü](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)
* Kuantum hata düzeltmesi: [bit çevirme hatası düzeltme kodu](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)
* [Aşama tahmini](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)
* Kuantum aritmetiği: [elde dalgalı toplayıcı oluşturma](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)

### <a name="entanglement-games"></a>Dolaşıklık oyunları

* [CHSH oyunu](https://github.com/microsoft/QuantumKatas/tree/master/CHSHGame)
* [GHZ oyunu](https://github.com/microsoft/QuantumKatas/tree/master/GHZGame)
* [Mermin-Peres sihirli kare oyunu](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)

## <a name="resources"></a>Kaynaklar

* [Kuantum Kataları](https://github.com/microsoft/QuantumKatas)'nın tam serisine bakın
* [Kataları çevrimiçi çalıştırın](https://aka.ms/try-quantum-katas)
