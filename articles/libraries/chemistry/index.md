---
title: Kuantum Kimyası Paketi Tanıtımı | Microsoft Docs
description: Kuantum Kimyası Paketi Tanıtımı
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: e5a9dd70874f1ae0baf4b781346278195a980a7e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960416"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Kuantum Kimyası Kitaplığı Tanıtımı

Fiziksel sistemlerin simülasyonu, uzun süredir kuantum işlemde merkezi bir rol oynamaktadır.  Bu, sistem simülasyonunun karmaşıklığının söz konusu kuantum sisteminin boyutuyla katlanarak büyümesiyle kuantum dinamikleri simülasyonlarının kuantum bilgisayarlarda yapılamayacak kadar zor olduğu düşünüldüğündendir.  Kimya ve malzeme biliminde sorunların simülasyonunun yapılması kuantum işlemi en fazla çağrıştıran kullanımdır. Bu, şu ana kadar simülasyonunun yapılması mümkün olmayan kimyasal tepkime mekanizmalarını araştırmamıza olanak tanır.  Yüksek sıcaklıkta çalışabilen süper iletkenler gibi ilişkili elektronik malzemelerin simülasyonunu yapmamıza da olanak tanır. Bu alandaki uygulamaların listesi oldukça büyüktür.

Bu belgenin amacı, kuantum bilgisayarlardaki elektronik yapı sorunlarının simülasyonunu yapmaya yönelik kısa bir tanıtıcı sunup okuyucunun Hamiltonian simülasyon kitaplığının birçok yönünün uzayda oynadığı rolü anlamasını sağlamaktır.  Kuantum mekaniklerine yönelik kısa bir tanıtım ile başlayıp elektronik sistemlerin bunda nasıl modellendiğini ele alacağız.  Ardından, bu tür kuantum dinamiklerinin bir kuantum bilgisayar kullanılarak nasıl öykünülebileceğini tartışacağız.  Bu tamamlandıktan sonra, kuantum dinamiklerini basit geçit dizilerinde derlemek için kullanılan iki yöntemi işleyeceğiz: Trotter-Suzuki ayrıştırmaları ve qubit’leştirmesi.
