---
title: Quantum Machine Learning Paketi Tanıtımı | Microsoft Docs
description: Quantum Machine Learning Paketi Tanıtımı
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
ms.openlocfilehash: 7f22d5d3212890abc764f88693937b534466170f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907860"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>Quantum Machine Learning Kitaplığı Tanıtımı

Quantum Machine Learning Kitaplığı, Q# dilinde yazılmış ve hibrit kuantum/klasik makine öğrenimi denemeleri çalıştırmanıza olanak tanıyan bir API’dir. Kitaplık size şu yetenekleri sağlar:

- Kuantum simülatörleri ile sınıflandırmak için kendi verilerinizi yükleme

- Kuantum makine öğrenimi alanına giriş yapmak için örnek ve öğreticileri kullanma

Geçerli klasik makine öğrenimi çerçeveleri ile karşılaştırıldığında düşük performans bekleyebilirsiniz (her şeyin zaten işlemsel olarak yüksek maliyetli olan bir kuantum cihazı simülasyonu üzerinde çalıştığını unutmayın).

Bu belgenin amacı:

- Hibrit kuantum/klasik öğrenim için (Q\# ile yazılmış) makine öğrenimi araçlarına kısa bir giriş.
- Makine öğrenimi kavramlarını ve özellikle de kuantum devresi merkezli sınıflandırıcılara (kuantum sıralı sınıflandırıcılar olarak da bilinir) giriş.
- Kitaplık tarafından sunulan araçları kullanmaya başlamak için temel bilgiler hakkında bir öğretici kümesi sağlama.
- Bu tür sınıflandırıcılara yönelik eğitim ve doğrulama yöntemlerini ve bunların, kitaplık tarafından sunulan belirli Q\# işlemlerine nasıl çevrilebileceğini inceleme.

Bu kitaplıkta uygulanan model, [Devre merkezli kuantum sınıflandırıcıları](https://arxiv.org/abs/1804.00633) içinde sunulan kuantum-klasik eğitim düzenine dayalıdır
