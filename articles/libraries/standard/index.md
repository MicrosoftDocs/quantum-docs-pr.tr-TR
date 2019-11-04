---
title: Q# standart kitaplıklar - tanıtım | Microsoft Docs
description: Q# standart kitaplıklar - tanıtım
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 547f4f6066e3ead627cd2a5970b1555999e988bb
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73056376"
---
# <a name="introduction-to-the-q-standard-libraries"></a><span data-ttu-id="75af2-103">Q# Standart Kitaplıklarına giriş</span><span class="sxs-lookup"><span data-stu-id="75af2-103">Introduction to the Q# Standard Libraries</span></span> #

<span data-ttu-id="75af2-104">Q#, Q# *standart kitaplıklarını* oluşturan çeşitli yararlı işlem, işlev ve kullanıcı tanımlı tür aralığı tarafından desteklenir.</span><span class="sxs-lookup"><span data-stu-id="75af2-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="75af2-105">[Kurulum ve doğrulama](xref:microsoft.quantum.install) esnasında yüklenen [ `Microsoft.Quantum.Development.Kit`NuGet paketi](https://www.nuget.org/packages/microsoft.quantum.development.kit) Q# derleyicisini ve hedef makineler tarafından uygulanan standart kitaplığın parçalarını sağlar.</span><span class="sxs-lookup"><span data-stu-id="75af2-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="75af2-106">[`Microsoft.Quantum.Standard` paketi](https://www.nuget.org/packages/microsoft.quantum.standard), hedef makineler arasında taşınabilen Q# standart kitaplıklarının bir kısmını sağlar.</span><span class="sxs-lookup"><span data-stu-id="75af2-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="75af2-107">Q# standart kitaplıkları tarafından tanımlanan semboller [API belgelerinde](xref:microsoft.quantum.standardlibsintro) çok daha ayrıntılı bir şekilde tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="75af2-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="75af2-108">Aşağıdaki bölümlerde, standart kitaplığın her parçasının en iyi özelliklerinin özetini çıkarıp her özelliğin pratikte nasıl kullanılabileceğine yönelik bağlam sunacağız.</span><span class="sxs-lookup"><span data-stu-id="75af2-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
