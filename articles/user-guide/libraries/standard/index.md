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
# <a name="introduction-to-the-no-locq-standard-libraries"></a><span data-ttu-id="67cf6-103">Q# Standart Kitaplıklarına giriş</span><span class="sxs-lookup"><span data-stu-id="67cf6-103">Introduction to the Q# Standard Libraries</span></span>

<span data-ttu-id="67cf6-104">Q#, Q# *standart kitaplıklarını* oluşturan çeşitli yararlı işlemler, işlevler ve kullanıcı tanımlı türler tarafından desteklenir.</span><span class="sxs-lookup"><span data-stu-id="67cf6-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="67cf6-105">[Yükleme ve doğrulama](xref:microsoft.quantum.install) sırasında yüklenen [`Microsoft.Quantum.Development.Kit`NuGet paketi](https://www.nuget.org/packages/microsoft.quantum.development.kit) Q# derleyicisini ve hedef makineler tarafından uygulanan standart kitaplığın parçalarını sağlar.</span><span class="sxs-lookup"><span data-stu-id="67cf6-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="67cf6-106">[`Microsoft.Quantum.Standard` paketi](https://www.nuget.org/packages/microsoft.quantum.standard), Q# standart kitaplıklarının hedef makineler arasında taşınabilen kısmını sağlar.</span><span class="sxs-lookup"><span data-stu-id="67cf6-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="67cf6-107">Q# standart kitaplıkları tarafından tanımlanan semboller, [API belgelerinde](xref:microsoft.quantum.apiref-intro) çok daha ayrıntılı bir şekilde tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="67cf6-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.apiref-intro).</span></span>

<span data-ttu-id="67cf6-108">Aşağıdaki bölümlerde, standart kitaplığın her parçasının en iyi özelliklerinin özetini çıkarıp her özelliğin pratikte nasıl kullanılabileceğine yönelik bağlam sunacağız.</span><span class="sxs-lookup"><span data-stu-id="67cf6-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
