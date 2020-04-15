---
title: Quantum Geliştirme Seti Kitaplıkları
description: Microsoft Quantum Geliştirme Seti’ne eklenen standart, kimya ve sayısal kitaplıklara genel bakış.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 89612aaa5c11e1a5e0d418256e96366953fdd3fe
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/13/2020
ms.locfileid: "77906415"
---
# <a name="overview-of-q-libraries"></a><span data-ttu-id="28bf2-103">Q# Kitaplıklarına Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="28bf2-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="28bf2-104">Q#’de kuantum uygulamaları geliştirmeyi kolaylaştırmak için Quantum Development Kit ile birlikte birkaç kitaplık sunulur.</span><span class="sxs-lookup"><span data-stu-id="28bf2-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="28bf2-105">Belgenin bu bölümünde bu kitaplıkları ve bunları programlarınızda kullanmayı açıklayacağız.</span><span class="sxs-lookup"><span data-stu-id="28bf2-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="28bf2-106">[**Standart kitaplıklar**](xref:microsoft.quantum.libraries.standard.intro): Bu bölümde, Q# programları ve hedef makineler arasındaki arabirimi açıklayan giriş bölümü ve Q# programları yazarken kullanılabilen genel amaçlı işlemleri ve işlevleri sağlayan Q# kitaplığı Canon açıklanır.</span><span class="sxs-lookup"><span data-stu-id="28bf2-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="28bf2-107">[**Kuantum kimyası kitaplığı**](xref:microsoft.quantum.chemistry.concepts.intro): Bu bölümde, fermiyonik Hamiltonian’ların yükleme gösterimlerine yönelik bir veri modeli sağlayan kuantum kimyası kitaplığı ve bu gösterimler üzerinde eylem gerçekleştiren kuantum simülasyonu işlemleri ve işlevleri açıklanır.</span><span class="sxs-lookup"><span data-stu-id="28bf2-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="28bf2-108">[**Kuantum sayıları kitaplığı**](xref:microsoft.quantum.numerics.intro): Bu bölümde, çeşitli matematiksel işlevlere yönelik uygulamaları sağlayan kuantum sayıları kitaplığı açıklanır.</span><span class="sxs-lookup"><span data-stu-id="28bf2-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="28bf2-109">Bu, tamsayıları (işaretli ve işaretsiz) ve sabit noktalı gösterimleri destekler.</span><span class="sxs-lookup"><span data-stu-id="28bf2-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>

<span data-ttu-id="28bf2-110">Kitaplıkların kaynaklarını ve kod örneklerini GitHub’dan edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="28bf2-110">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span> <span data-ttu-id="28bf2-111">Daha fazla bilgi için [lisanslama](xref:microsoft.quantum.libraries.licensing) bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="28bf2-111">See also the [licensing](xref:microsoft.quantum.libraries.licensing) section for further information.</span></span> <span data-ttu-id="28bf2-112">Paket başvurularının (“ikililer”), kitaplıkları projelere eklemeye yönelik farklı bir yol sunan kitaplıklar için de kullanılabilir olduğu unutulmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="28bf2-112">It should be noted that package references ("binaries") are available also for the libraries which offers another way of including the libraries in projects.</span></span> <span data-ttu-id="28bf2-113">Bunları [NuGet](https://nuget.org) aracılığıyla da kolayca edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="28bf2-113">A convenient way of obtaining them is via [nuget](https://nuget.org).</span></span>
