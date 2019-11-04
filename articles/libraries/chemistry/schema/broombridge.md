---
title: Broombridge-hisse dili yanlış deneme şeması
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: c2a7636d0b3f07419e3312e04da5d811229ad854
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185333"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge hisse Chemistry şeması # 

[Nwchem](http://www.nwchem-sw.org/) gibi güçlü hesaplama Kimya yazılımı, çok çeşitli gerçek dünya Kimya sorunlarını modelleyebilir. Microsoft hisse dili Mistry kitaplığı ile NWChem molesel modellere erişmek için, **Brombridge**' i çağırdığımız bir [YAML](https://en.wikipedia.org/wiki/YAML)tabanlı şema kullanırız. Ad, bazı çemberlerde Hamiltonians 'in bir doğulu olarak ünkülbir yerde yer aldığı bir [yer işaretine](https://en.wikipedia.org/wiki/Broom_Bridge) başvuru olarak seçilmiştir. 

[Nwchem](https://github.com/nwchemgit/nwchem) , Izin verilen eğitim topluluk lisansı (ECL) 2,0 lisansı kapsamında lisanslanan açık kaynaklı bir projem. Broombridge, [burada](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) belirtilen bir açık kaynak şemadır ve bu, [RFC 2119](https://tools.ietf.org/html/rfc2119) ' de ve MIT License kapsamında lisanslanan [Doğrulayıcı betiğinin](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) ardından bir [tanım](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) ile birlikte sunulur. 

YAML tabanlı, Broombridge, elektronik yapı sorunlarını temsil eden yapılandırılmış, okunabilir ve insan tarafından düzenlenebilir bir yoldur. Özellikle, aşağıdaki veriler temsil edilebilir: 
- Fermıonic Hamiltonians, tek ve iki elektron integralleri kullanılarak gösterilebilir. 
- Zemin ve heyecanlı durumlar, oluşturma dizileri kullanılarak sunulabilir.
- Enerji düzeylerinin üst ve alt sınırları belirtilebilir.

Veri biçimi, daha kolay bir şekilde NWChem 'ten oluşturulabilir: Bu, [burada](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) sağlananları ve çalıştırmanın parçası olarak çıkış Broombridge 'yi bir Docker üzerinden çalıştırmak Için nwchem 'nin tam yüklemesinden farklı yöntemler sunulmaktadır Kimya Decks 'ten brombridge oluşturmak için de kullanılabilecek nwchem görüntüsü. Son olarak, herhangi bir kimya yazılımı yüklemeye gerek kalmadan hızla hesaplama kimya ile çalışmaya başlamak için bir görsel Yöntem nwchem için [emsl okları](https://arrows.emsl.pnnl.gov/api/qsharp_chem) arabirimi tarafından sağlanır. 

Yüksek düzeyde, NWChem ve Microsoft Quantum Development Kit arasındaki karşılıklı yürütme şu şekilde görselleştirilir: ![Chemistry yığını](~/media/broombridge.png) mavi gölgeli kutu Brocimbridge şemasını temsil ediyorsa, çeşitli gri gölgeli kutular diğer iç ilişkileri temsil eder Gerçek Dünya Kimya sorunlarına dayalı olarak hesaplama Kimya için hisse algoritmaları temsil etmek ve işlemek üzere seçilmiş veri gösterimleri. 

Broombridge şeması kullanılarak tanımlanan birden çok kimyasal temsili [burada](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)verilmiştir.

