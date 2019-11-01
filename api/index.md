---
uid: microsoft.quantum.standardlibsintro
title: Microsoft Quantum için Q# standart kitaplığı
description: Microsoft Quantum için Q# standart kitaplığı başvuru belgeleri
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999091"
---
# <a name="q-standard-libraries"></a><span data-ttu-id="93ab8-103">Q# standart kitaplıkları</span><span class="sxs-lookup"><span data-stu-id="93ab8-103">Q# standard libraries</span></span> #

<span data-ttu-id="93ab8-104">Q#, Q# *standart kitaplığını* oluşturan çeşitli yararlı işlem, işlev ve kullanıcı tanımlı tür aralığı tarafından desteklenir.</span><span class="sxs-lookup"><span data-stu-id="93ab8-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="93ab8-105">Q# standart kitaplığı iki ana bölüme ayrılır:</span><span class="sxs-lookup"><span data-stu-id="93ab8-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="93ab8-106">**Giriş**: genellikle klasik yerel .NET kodunda hedef makinenin ve derleyicinin bir parçası olarak tanımlanan işlemler ve işlevler.</span><span class="sxs-lookup"><span data-stu-id="93ab8-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="93ab8-107">Genel olarak, farklı hedef makineler her bir sisteme uygun olan farklı giriş uygulamalarına sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="93ab8-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="93ab8-108">**Esas**: girişte tanımlanan mantık üzerinde oluşturulan Q# dilinde tanımlanmış işlemler ve işlevler.</span><span class="sxs-lookup"><span data-stu-id="93ab8-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="93ab8-109">Esas uygulama, hedef makinelere göre belirsizdir.</span><span class="sxs-lookup"><span data-stu-id="93ab8-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="93ab8-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="93ab8-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>