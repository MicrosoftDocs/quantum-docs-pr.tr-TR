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
# <a name="introduction-to-the-no-locq-standard-libraries"></a><span data-ttu-id="10221-103">Q# Standart Kitaplıklarına giriş</span><span class="sxs-lookup"><span data-stu-id="10221-103">Introduction to the Q# Standard Libraries</span></span>

<span data-ttu-id="10221-104">Q#, Q# *standart kitaplıklarını* oluşturan çeşitli yararlı işlemler, işlevler ve kullanıcı tanımlı türler tarafından desteklenir.</span><span class="sxs-lookup"><span data-stu-id="10221-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="10221-105">[Yükleme ve doğrulama](xref:microsoft.quantum.install) sırasında yüklenen [`Microsoft.Quantum.Development.Kit`NuGet paketi](https://www.nuget.org/packages/microsoft.quantum.development.kit) Q# derleyicisini ve hedef makineler tarafından uygulanan standart kitaplığın parçalarını sağlar.</span><span class="sxs-lookup"><span data-stu-id="10221-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="10221-106">[`Microsoft.Quantum.Standard` paketi](https://www.nuget.org/packages/microsoft.quantum.standard), Q# standart kitaplıklarının hedef makineler arasında taşınabilen kısmını sağlar.</span><span class="sxs-lookup"><span data-stu-id="10221-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="10221-107">Q# standart kitaplıkları tarafından tanımlanan semboller, [API belgelerinde](xref:microsoft.quantum.standardlibsintro) çok daha ayrıntılı bir şekilde tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="10221-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="10221-108">Aşağıdaki bölümlerde, standart kitaplığın her parçasının en iyi özelliklerinin özetini çıkarıp her özelliğin pratikte nasıl kullanılabileceğine yönelik bağlam sunacağız.</span><span class="sxs-lookup"><span data-stu-id="10221-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
