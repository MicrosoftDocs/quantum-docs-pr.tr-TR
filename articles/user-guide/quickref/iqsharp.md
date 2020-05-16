---
title: IQ# Magic Komutları
description: 'Q # Jupyıter Not defterleri ile IQ # Magic komutları için hızlı başvuru sayfası'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431028"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="488ea-103">IQ# Magic Komutları</span><span class="sxs-lookup"><span data-stu-id="488ea-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="488ea-104">Genel</span><span class="sxs-lookup"><span data-stu-id="488ea-104">General</span></span>

- <span data-ttu-id="488ea-105">`%config`: Yapılandırma tercihlerini ayarlar veya alır.</span><span class="sxs-lookup"><span data-stu-id="488ea-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="488ea-106">`%estimate`: Belirtilen işlevi veya işlemi, miktar Tumsimülatör hedef makinesinde çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="488ea-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="488ea-107">`%lsmagic`: Şu anda kullanılabilir olan tüm sihirli komutlarının listesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="488ea-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="488ea-108">`%package`: Bir NuGet paketini yükleme özelliği sağlar.</span><span class="sxs-lookup"><span data-stu-id="488ea-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="488ea-109">`%performance`: Bu çekirdek için geçerli performans ölçümlerini raporlar.</span><span class="sxs-lookup"><span data-stu-id="488ea-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="488ea-110">`%simulate`: Belirtilen işlevi veya işlemi, miktar Tumsimülatör hedef makinesinde çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="488ea-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="488ea-111">`%toffoli`: Toffzeytin simülatör hedef makinesi üzerinde belirli bir işlevi veya işlemi çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="488ea-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="488ea-112">`%who`: Geçerli çalışma alanıyla ilgili eylemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="488ea-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="488ea-113">`%workspace`: Etkileşimli veya geçerli çalışma alanından yüklenen geçerli oturumda tanımlanan tüm işlem ve işlevlerin listesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="488ea-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="488ea-114">Kimya</span><span class="sxs-lookup"><span data-stu-id="488ea-114">Chemistry</span></span>

- <span data-ttu-id="488ea-115">`%chemistry.broombridge`: Belirli bir. YAML dosyasından Broombridge elektronik yapısı sorun gösterimini yükler ve döndürür.</span><span class="sxs-lookup"><span data-stu-id="488ea-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="488ea-116">`%chemistry.encode`: Bir fermıon Hamiltonian 'yi, Q # tarafından tüketilen bir biçime kodluyor.</span><span class="sxs-lookup"><span data-stu-id="488ea-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="488ea-117">`%chemistry.fh.add_terms`: Bir fermıon Hamiltonian için terimler ekler.</span><span class="sxs-lookup"><span data-stu-id="488ea-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="488ea-118">`%chemistry.fh.load`: Elektronik bir yapı sorunu için fermıon Hamiltonian 'i yükler.</span><span class="sxs-lookup"><span data-stu-id="488ea-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="488ea-119">Sorun bir dosyadan yüklenir veya bağımsız değişken olarak geçirilir.</span><span class="sxs-lookup"><span data-stu-id="488ea-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="488ea-120">`%chemistry.inputstate.load`: Broombridge elektronik yapısı sorununu yükler ve seçili giriş durumunu döndürür.</span><span class="sxs-lookup"><span data-stu-id="488ea-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="488ea-121">Microsoft. hisse. katas paketinden</span><span class="sxs-lookup"><span data-stu-id="488ea-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="488ea-122">`%kata`: Tek bir test yürütür ve testin başarıyla başarılı olup olmadığını bildirir.</span><span class="sxs-lookup"><span data-stu-id="488ea-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="488ea-123">`%check_kata`: Tek bir küta 'nın test için başvuru uygulamasını denetler.</span><span class="sxs-lookup"><span data-stu-id="488ea-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="488ea-124">Özellikle, tek bir görev için başvuru uygulamasını hücreye koyar ve testin başarıyla başarılı olup olmadığını bildirir.</span><span class="sxs-lookup"><span data-stu-id="488ea-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
