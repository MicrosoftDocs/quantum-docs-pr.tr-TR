---
title: Kuantum Kimyası Kitaplığı Tanıtımı
description: Microsoft Quantum Kimya Kitaplığı hakkında bilgi edinin ve kuantum bilgisayarlarda elektronik yapı sorunlarının benzetimini nasıl yaptığını öğrenin.
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3fa606600db1641b9f8b86ccefebb7681f181b92
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847480"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a><span data-ttu-id="edabd-103">Kuantum Kimyası Kitaplığı Tanıtımı</span><span class="sxs-lookup"><span data-stu-id="edabd-103">Introduction to the Quantum Chemistry Library</span></span>

<span data-ttu-id="edabd-104">Fiziksel sistemlerin simülasyonu, uzun süredir kuantum işlemde merkezi bir rol oynamaktadır.</span><span class="sxs-lookup"><span data-stu-id="edabd-104">Simulation of physical systems has long played a central role in quantum computing.</span></span>  <span data-ttu-id="edabd-105">Bu, sistem simülasyonunun karmaşıklığının söz konusu kuantum sisteminin boyutuyla katlanarak büyümesiyle kuantum dinamikleri simülasyonlarının kuantum bilgisayarlarda yapılamayacak kadar zor olduğu düşünüldüğündendir.</span><span class="sxs-lookup"><span data-stu-id="edabd-105">This is because quantum dynamics are widely believed to be intractable to simulate on quantum computers, meaning that the complexity of simulating the system scales exponentially with the size of the quantum system in question.</span></span>  <span data-ttu-id="edabd-106">Kimya ve malzeme biliminde sorunların simülasyonunun yapılması kuantum işlemi en fazla çağrıştıran kullanımdır. Bu, şu ana kadar simülasyonunun yapılması mümkün olmayan kimyasal tepkime mekanizmalarını araştırmamıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="edabd-106">Simulating problems in chemistry and material science remains perhaps the most evocative application of quantum computing and would allow us to probe chemical reaction mechanisms that hitherto were beyond our ability to measure or simulate.</span></span>  <span data-ttu-id="edabd-107">Yüksek sıcaklıkta çalışabilen süper iletkenler gibi ilişkili elektronik malzemelerin simülasyonunu yapmamıza da olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="edabd-107">It would also allow us to simulate correlated electronic materials such as high-temperature superconductors.</span></span> <span data-ttu-id="edabd-108">Bu alandaki uygulamaların listesi oldukça büyüktür.</span><span class="sxs-lookup"><span data-stu-id="edabd-108">The list of applications in this space is vast.</span></span>

<span data-ttu-id="edabd-109">Bu belgenin amacı, kuantum bilgisayarlardaki elektronik yapı sorunlarının simülasyonunu yapmaya yönelik kısa bir tanıtıcı sunup okuyucunun Hamiltonian simülasyon kitaplığının birçok yönünün uzayda oynadığı rolü anlamasını sağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="edabd-109">The purpose of this documentation is to provide a concise introduction to simulating electronic structure problems on quantum computers in order to help the reader understand the role that many aspects of the Hamiltonian simulation library play within the space.</span></span>  <span data-ttu-id="edabd-110">Kuantum mekaniklerine yönelik kısa bir tanıtım ile başlayıp elektronik sistemlerin bunda nasıl modellendiğini ele alacağız.</span><span class="sxs-lookup"><span data-stu-id="edabd-110">We begin with a brief introduction to quantum mechanics and then proceed to discuss how electronic systems are modeled in it.</span></span>  <span data-ttu-id="edabd-111">Ardından, bu tür kuantum dinamiklerinin bir kuantum bilgisayar kullanılarak nasıl öykünülebileceğini tartışacağız.</span><span class="sxs-lookup"><span data-stu-id="edabd-111">We will then discuss how such quantum dynamics can be emulated using a quantum computer.</span></span>  <span data-ttu-id="edabd-112">Bu tamamlandıktan sonra, kuantum dinamiklerini basit geçit dizilerinde derlemek için kullanılan iki yöntemi işleyeceğiz: Trotter-Suzuki ayrıştırmaları ve qubit’leştirmesi.</span><span class="sxs-lookup"><span data-stu-id="edabd-112">Once this is complete we will discuss two methods used to compile the quantum dynamics to sequences of elementary gates: Trotter-Suzuki decompositions and qubitization.</span></span>
