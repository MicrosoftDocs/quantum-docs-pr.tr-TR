---
title: Microsoft Q# standart kitaplıklarına giriş
description: Kuantum programlarında kullanılan işlemleri, işlevleri ve veri türlerini tanımlayan Microsoft Q# standart kitaplıkları hakkında bilgi edinin.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 820ad885e7134aa723116d4c9f853d88210a5514
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907163"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Q# Standart Kitaplıklarına giriş #

Q#, Q# *standart kitaplıklarını* oluşturan çeşitli yararlı işlem, işlev ve kullanıcı tanımlı tür aralığı tarafından desteklenir.
[Kurulum ve doğrulama](xref:microsoft.quantum.install) esnasında yüklenen [`Microsoft.Quantum.Development.Kit`NuGet paketi](https://www.nuget.org/packages/microsoft.quantum.development.kit) Q# derleyicisini ve hedef makineler tarafından uygulanan standart kitaplığın parçalarını sağlar.
[`Microsoft.Quantum.Standard` paketi](https://www.nuget.org/packages/microsoft.quantum.standard), hedef makineler arasında taşınabilen Q# standart kitaplıklarının bir kısmını sağlar.

Q# standart kitaplıkları tarafından tanımlanan semboller [API belgelerinde](xref:microsoft.quantum.standardlibsintro) çok daha ayrıntılı bir şekilde tanımlanır.

Aşağıdaki bölümlerde, standart kitaplığın her parçasının en iyi özelliklerinin özetini çıkarıp her özelliğin pratikte nasıl kullanılabileceğine yönelik bağlam sunacağız.
