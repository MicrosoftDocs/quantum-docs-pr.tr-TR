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
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="e8c98-103">Quantum Machine Learning Kitaplığı Tanıtımı</span><span class="sxs-lookup"><span data-stu-id="e8c98-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="e8c98-104">Quantum Machine Learning Kitaplığı, Q# dilinde yazılmış ve hibrit kuantum/klasik makine öğrenimi denemeleri çalıştırmanıza olanak tanıyan bir API’dir.</span><span class="sxs-lookup"><span data-stu-id="e8c98-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="e8c98-105">Kitaplık size şu yetenekleri sağlar:</span><span class="sxs-lookup"><span data-stu-id="e8c98-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="e8c98-106">Kuantum simülatörleri ile sınıflandırmak için kendi verilerinizi yükleme</span><span class="sxs-lookup"><span data-stu-id="e8c98-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="e8c98-107">Kuantum makine öğrenimi alanına giriş yapmak için örnek ve öğreticileri kullanma</span><span class="sxs-lookup"><span data-stu-id="e8c98-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="e8c98-108">Geçerli klasik makine öğrenimi çerçeveleri ile karşılaştırıldığında düşük performans bekleyebilirsiniz (her şeyin zaten işlemsel olarak yüksek maliyetli olan bir kuantum cihazı simülasyonu üzerinde çalıştığını unutmayın).</span><span class="sxs-lookup"><span data-stu-id="e8c98-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="e8c98-109">Bu belgenin amacı:</span><span class="sxs-lookup"><span data-stu-id="e8c98-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="e8c98-110">Hibrit kuantum/klasik öğrenim için (Q\# ile yazılmış) makine öğrenimi araçlarına kısa bir giriş.</span><span class="sxs-lookup"><span data-stu-id="e8c98-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="e8c98-111">Makine öğrenimi kavramlarını ve özellikle de kuantum devresi merkezli sınıflandırıcılara (kuantum sıralı sınıflandırıcılar olarak da bilinir) giriş.</span><span class="sxs-lookup"><span data-stu-id="e8c98-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="e8c98-112">Kitaplık tarafından sunulan araçları kullanmaya başlamak için temel bilgiler hakkında bir öğretici kümesi sağlama.</span><span class="sxs-lookup"><span data-stu-id="e8c98-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="e8c98-113">Bu tür sınıflandırıcılara yönelik eğitim ve doğrulama yöntemlerini ve bunların, kitaplık tarafından sunulan belirli Q\# işlemlerine nasıl çevrilebileceğini inceleme.</span><span class="sxs-lookup"><span data-stu-id="e8c98-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="e8c98-114">Bu kitaplıkta uygulanan model, [Devre merkezli kuantum sınıflandırıcıları](https://arxiv.org/abs/1804.00633) içinde sunulan kuantum-klasik eğitim düzenine dayalıdır</span><span class="sxs-lookup"><span data-stu-id="e8c98-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
