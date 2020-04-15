---
title: Kuantum kimyası örnek uygulamaları
description: Microsoft Quantum kimya kitaplığının örnek uygulamalarını keşfedin.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/13/2020
ms.locfileid: "77906500"
---
# <a name="quantum-chemistry-examples"></a>Kuantum kimyası örnekleri

Kuantum kimyası kavramlarında, el ile örnek fermion Hamiltonian’ları oluşturduk. Artık, [Hamiltonian dinamiklerinin simülasyonunu yapma](xref:microsoft.quantum.libraries.standard.algorithms) bölümünde özetlenen kimya simülasyonu algoritmalarını canon kitaplığındaki [kuantum aşaması tahmini](xref:microsoft.quantum.libraries.characterization) ile birleştiriyoruz. Bu birleşim, temsil edilen moleküldeki enerji düzeylerine yönelik tahmin elde etmemize olanak tanır. Bu, bir kuantum bilgisayardaki kuantum kimyasının önemli uygulamalarından biridir. 

Hamiltonian’ın koşullarını tek tek belirtmek yerine, ölçeğe uygun kimya denemeleri gerçekleştirmemize olanak tanıyan bazı örneklerle de çalışırız. Hamiltonian’ın [Broombridge şemasında](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) kodladığı bir kimyayı yükleyerek başlayacağız.

Simülasyonu [Tam durumlu simülatörde](xref:microsoft.quantum.machines.full-state-simulator) yapılamayacak kadar büyük olan moleküllerde ilgi çekici bilimler hala gerçekleştirilebilir. Örneğin, büyük kimya simülasyonu gerçekleştirmeye yönelik kaynak maliyetleri [izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) hedeflenerek değerlendirilebilir.

Şimdi, sağlanan örneklerin bazıları ile kimya simülasyonu kitaplığının ilgi çekici uygulamalarını göstereceğiz.
