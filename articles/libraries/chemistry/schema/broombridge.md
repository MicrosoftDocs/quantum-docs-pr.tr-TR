---
title: Broombridge-hisse dili yanlış deneme şeması
description: Microsoft Quantum Development Kit ile gerçek dünya Kimya sorunlarını modellemek için kullanılan broombridge hisse Kimya şemasına genel bakış.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: a746b63055bb1b2c1168b89993a7459ca9597f86
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907826"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge hisse Chemistry şeması # 

[Nwchem](http://www.nwchem-sw.org/) gibi güçlü hesaplama Kimya yazılımı, çok çeşitli gerçek dünya Kimya sorunlarını modelleyebilir. Microsoft hisse dili Mistry kitaplığı ile NWChem molesel modellere erişmek için, **Brombridge**' i çağırdığımız bir [YAML](https://en.wikipedia.org/wiki/YAML)tabanlı şema kullanırız. Ad, bazı çemberlerde Hamiltonians 'in bir doğulu olarak ünkülbir yerde yer aldığı bir [yer işaretine](https://en.wikipedia.org/wiki/Broom_Bridge) başvuru olarak seçilmiştir. 

[Nwchem](https://github.com/nwchemgit/nwchem) , Izin verilen eğitim topluluk lisansı (ECL) 2,0 lisansı kapsamında lisanslanan açık kaynaklı bir projem. Broombridge, [burada](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) belirtilen bir açık kaynak şemadır ve bu, [RFC 2119](https://tools.ietf.org/html/rfc2119) ' de ve MIT License kapsamında lisanslanan [Doğrulayıcı betiğinin](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) ardından bir [tanım](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) ile birlikte sunulur. 

YAML tabanlı, Broombridge, elektronik yapı sorunlarını temsil eden yapılandırılmış, okunabilir ve insan tarafından düzenlenebilir bir yoldur. Özellikle, aşağıdaki veriler temsil edilebilir: 
- Fermıonic Hamiltonians, tek ve iki elektron integralleri kullanılarak gösterilebilir. 
- Zemin ve heyecanlı durumlar, oluşturma dizileri kullanılarak sunulabilir.
- Enerji düzeylerinin üst ve alt sınırları belirtilebilir.

Veri biçimi, NWChem 'ten daha kolay kolay bir şekilde oluşturulabilir: NWChem 'nin tam yüklemesinden, [burada](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) sağlananlara ve çalıştırmanın parçası olarak çıktı Brombridge 'e kadar çeşitli yöntemler ve bu da pmistry Decks 'Ten brombridge 'i oluşturmak için de kullanılabilecek bir Docker görüntüsü üzerinden kullanılabilir. Son olarak, herhangi bir kimya yazılımı yüklemeye gerek kalmadan hızla hesaplama kimya ile çalışmaya başlamak için bir görsel Yöntem nwchem için [emsl okları](https://arrows.emsl.pnnl.gov/api/qsharp_chem) arabirimi tarafından sağlanır. 

Yüksek düzeyde, nwchem ve Microsoft Quantum Development Kit arasında karşılıklı yürütme şu şekilde görselleştirilir: ![Kimya Stack](~/media/broombridge.png) mavi gölgeli kutu brocimbridge şemasını temsil ediyorsa, çeşitli gri gölgeli kutular, gerçek dünya Kimya sorunlarını temel alan hesaplama Kimya için, ücretlerini temsil etmek ve işlemek üzere seçilen diğer iç veri sunumlarını temsil eder. 

Broombridge şeması kullanılarak tanımlanan birden çok kimyasal temsili [burada](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)verilmiştir.
