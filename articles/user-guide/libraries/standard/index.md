---
title: Microsoft Q# standart kitaplıklarına giriş
description: Kuantum programlarında kullanılan işlemleri, işlevleri ve veri türlerini tanımlayan Microsoft Q# standart kitaplıkları hakkında bilgi edinin.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 58e271fefba84e45c5558eeee066bc37c22bf63b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858311"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Q# Standart Kitaplıklarına giriş

Q#, Q# *standart kitaplıklarını* oluşturan çeşitli yararlı işlemler, işlevler ve kullanıcı tanımlı türler tarafından desteklenir.
[Yükleme ve doğrulama](xref:microsoft.quantum.install) sırasında yüklenen [`Microsoft.Quantum.Development.Kit`NuGet paketi](https://www.nuget.org/packages/microsoft.quantum.development.kit) Q# derleyicisini ve hedef makineler tarafından uygulanan standart kitaplığın parçalarını sağlar.
[`Microsoft.Quantum.Standard` paketi](https://www.nuget.org/packages/microsoft.quantum.standard), Q# standart kitaplıklarının hedef makineler arasında taşınabilen kısmını sağlar.

Q# standart kitaplıkları tarafından tanımlanan semboller, [API belgelerinde](xref:microsoft.quantum.apiref-intro) çok daha ayrıntılı bir şekilde tanımlanır.

Aşağıdaki bölümlerde, standart kitaplığın her parçasının en iyi özelliklerinin özetini çıkarıp her özelliğin pratikte nasıl kullanılabileceğine yönelik bağlam sunacağız.
