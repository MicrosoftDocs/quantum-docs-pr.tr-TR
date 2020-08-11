---
title: Microsoft Q# standart kitaplıklarına giriş
description: Kuantum programlarında kullanılan işlemleri, işlevleri ve veri türlerini tanımlayan Microsoft Q# standart kitaplıkları hakkında bilgi edinin.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4db227fcf159331f9f8456c474ce6d64111c21df
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868483"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Q# Standart Kitaplıklarına giriş

Q#, Q# *standart kitaplıklarını* oluşturan çeşitli yararlı işlemler, işlevler ve kullanıcı tanımlı türler tarafından desteklenir.
[Yükleme ve doğrulama](xref:microsoft.quantum.install) sırasında yüklenen [`Microsoft.Quantum.Development.Kit`NuGet paketi](https://www.nuget.org/packages/microsoft.quantum.development.kit) Q# derleyicisini ve hedef makineler tarafından uygulanan standart kitaplığın parçalarını sağlar.
[`Microsoft.Quantum.Standard` paketi](https://www.nuget.org/packages/microsoft.quantum.standard), Q# standart kitaplıklarının hedef makineler arasında taşınabilen kısmını sağlar.

Q# standart kitaplıkları tarafından tanımlanan semboller, [API belgelerinde](xref:microsoft.quantum.standardlibsintro) çok daha ayrıntılı bir şekilde tanımlanır.

Aşağıdaki bölümlerde, standart kitaplığın her parçasının en iyi özelliklerinin özetini çıkarıp her özelliğin pratikte nasıl kullanılabileceğine yönelik bağlam sunacağız.
