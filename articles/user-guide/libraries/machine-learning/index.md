---
title: Quantum Machine Learning Paketi Tanıtımı | Microsoft Docs
description: Quantum Machine Learning Paketi Tanıtımı
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: conceptual
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1e36948a216a06d76b99cd451bbfac6f5defd7c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858787"
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
