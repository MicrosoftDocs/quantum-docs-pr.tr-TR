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
# <a name="introduction-to-the-quantum-chemistry-library"></a>Kuantum Kimyası Kitaplığı Tanıtımı

Fiziksel sistemlerin simülasyonu, uzun süredir kuantum işlemde merkezi bir rol oynamaktadır.  Bu, sistem simülasyonunun karmaşıklığının söz konusu kuantum sisteminin boyutuyla katlanarak büyümesiyle kuantum dinamikleri simülasyonlarının kuantum bilgisayarlarda yapılamayacak kadar zor olduğu düşünüldüğündendir.  Kimya ve malzeme biliminde sorunların simülasyonunun yapılması kuantum işlemi en fazla çağrıştıran kullanımdır. Bu, şu ana kadar simülasyonunun yapılması mümkün olmayan kimyasal tepkime mekanizmalarını araştırmamıza olanak tanır.  Yüksek sıcaklıkta çalışabilen süper iletkenler gibi ilişkili elektronik malzemelerin simülasyonunu yapmamıza da olanak tanır. Bu alandaki uygulamaların listesi oldukça büyüktür.

Bu belgenin amacı, kuantum bilgisayarlardaki elektronik yapı sorunlarının simülasyonunu yapmaya yönelik kısa bir tanıtıcı sunup okuyucunun Hamiltonian simülasyon kitaplığının birçok yönünün uzayda oynadığı rolü anlamasını sağlamaktır.  Kuantum mekaniklerine yönelik kısa bir tanıtım ile başlayıp elektronik sistemlerin bunda nasıl modellendiğini ele alacağız.  Ardından, bu tür kuantum dinamiklerinin bir kuantum bilgisayar kullanılarak nasıl öykünülebileceğini tartışacağız.  Bu tamamlandıktan sonra, kuantum dinamiklerini basit geçit dizilerinde derlemek için kullanılan iki yöntemi işleyeceğiz: Trotter-Suzuki ayrıştırmaları ve qubit’leştirmesi.
