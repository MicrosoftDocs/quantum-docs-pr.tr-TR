---
title: Broombridge hisse Chemistry şeması
description: Microsoft Quantum Development Kit ile gerçek dünya Kimya sorunlarını modellemek için kullanılan broombridge hisse Kimya şemasına genel bakış.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: 708c4277080c358cb35a49fbf1dde0394d331043
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022534"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge hisse Chemistry şeması # 

[Nwchem](http://www.nwchem-sw.org/) gibi güçlü hesaplama Kimya yazılımı, çok çeşitli gerçek dünya Kimya sorunlarını modeletmenize olanak tanır. Microsoft hisse dili Mistry kitaplığı ile NWChem molesel modellere erişmek için **Broombridge**adlı bir [YAML](https://en.wikipedia.org/wiki/YAML)tabanlı şema kullanırsınız. Ad, bazı çemberlerde Hamiltonians 'in bir doğulu olarak ünkülbir yerde yer aldığı bir [yer işaretine](https://en.wikipedia.org/wiki/Broom_Bridge) başvuru olarak seçilmiştir. 

[Nwchem](https://github.com/nwchemgit/nwchem) , Izin verilen eğitim topluluk lisansı (ECL) 2,0 lisansı kapsamında lisanslanan açık kaynaklı bir projem. [Broombridge hisse Chemistry şeması](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)), [RFC 2119](https://tools.ietf.org/html/rfc2119) ' den sonrakı bir [tanım](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) ve MIT Lisansı kapsamında lisanslanan bir [Doğrulayıcı betiği](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) içeren bir açık kaynak şemadır. 

YAML tabanlı, Broombridge, elektronik yapı sorunlarını temsil eden yapılandırılmış, okunabilir ve insan tarafından düzenlenebilir bir yoldur. Özellikle, aşağıdaki veriler temsil edilebilir:
- Fermıonic Hamiltonians, tek ve iki elektron integralleri kullanılarak gösterilebilir.
- Zemin ve heyecanlı durumlar, oluşturma dizileri kullanılarak sunulabilir.
- Enerji düzeylerinin üst ve alt sınırları belirtilebilir.

Çeşitli yöntemler kullanılarak nwchem öğesinden veri oluşturulabilir. nmistry Decks 'i çalıştırmak için nwchem 'ın tam yüklemesini kullanma (örneğin, çalıştırmanın bir parçası olarak çıktı olan [nwchem kitaplığı](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) 'nda sağlananları) veya bir Docker görüntüsü olan nwchem, kimya KIKS 'ten brombridge 'i oluşturmak için de kullanılabilecek. Herhangi bir kimya yazılımı yüklemeye gerek kalmadan hesaplama Kimya kullanmaya başlamak için, [emsl okları](https://arrows.emsl.pnnl.gov/api/qsharp_chem)tarafından sağlanmış olan nwchem için görsel arabirimi kullanabilirsiniz.

Yüksek düzeyde, nwchem ve Microsoft Quantum Development Kit arasında karşılıklı yürütme şu şekilde görselleştirilir: ![Kimya Stack](~/media/broombridge.png) mavi gölgeli kutu brocimbridge şemasını temsil ediyorsa, çeşitli gri gölgeli kutular, gerçek dünya Kimya sorunlarını temel alan hesaplama Kimya için, ücretlerini temsil etmek ve işlemek üzere seçilen diğer iç veri sunumlarını temsil eder.

Hisse geliştirme seti örnekleri deposundaki [Integral/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) klasörü, Broombridge şeması kullanılarak tanımlanmış birden çok kimyasal gösterimi içerir.
