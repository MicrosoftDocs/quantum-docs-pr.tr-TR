---
title: Microsoft Quantum geliştirme setini (QDK) ayarlama
description: Microsoft Quantum geliştirme setini farklı ortamlar için nasıl ayarlayacağınızı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834491"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="d7f00-103">Microsoft Quantum geliştirme setini (QDK) ayarlama</span><span class="sxs-lookup"><span data-stu-id="d7f00-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="d7f00-104">Kuantum programlamaya başlayabilmek amacıyla, Microsoft Quantum geliştirme setini (QDK) ortamınız için nasıl ayarlayacağınızı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="d7f00-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="d7f00-105">QDK aşağıdakilerden oluşur:</span><span class="sxs-lookup"><span data-stu-id="d7f00-105">The QDK consists of:</span></span>

- <span data-ttu-id="d7f00-106">Q# programlama dili</span><span class="sxs-lookup"><span data-stu-id="d7f00-106">The Q# programming language</span></span>
- <span data-ttu-id="d7f00-107">Q# dilindeki karmaşık işlevleri soyutlayan bir kitaplık seti</span><span class="sxs-lookup"><span data-stu-id="d7f00-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="d7f00-108">Q# dilinde yazılmış kuantum programlarını çalıştırmak için Python ve .NET dillerine (C#, F# ve VB.NET) yönelik API’ler</span><span class="sxs-lookup"><span data-stu-id="d7f00-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="d7f00-109">Geliştirmenizi kolaylaştıracak araçlar</span><span class="sxs-lookup"><span data-stu-id="d7f00-109">Tools to facilitate your development</span></span>

<span data-ttu-id="d7f00-110">Q# programları Visual Studio Code veya Visual Studio kullanarak, IQ# Jupyter çekirdeğine sahip Jupyter Not Defterleri aracılığıyla ya da Python veya .NET dilinde (C#, F#) yazılmış bir konak ortamıyla eşlenmiş bağımsız uygulamalar olarak çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="d7f00-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="d7f00-111">Q# programlarını [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) veya [Docker](#use-the-qdk-with-docker) kullanarak da çevrimiçi olarak çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d7f00-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="d7f00-112">QDK’yı ayarlama seçenekleri</span><span class="sxs-lookup"><span data-stu-id="d7f00-112">Options for setting up the QDK</span></span>

<span data-ttu-id="d7f00-113">QDK’yı üç şekilde kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="d7f00-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="d7f00-114">QDK’yı yerel olarak yükleyerek</span><span class="sxs-lookup"><span data-stu-id="d7f00-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="d7f00-115">QDK’yı çevrimiçi olarak kullanarak</span><span class="sxs-lookup"><span data-stu-id="d7f00-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="d7f00-116">QDK Docker görüntüsü kullanarak</span><span class="sxs-lookup"><span data-stu-id="d7f00-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="d7f00-117">QDK’yı yerel olarak yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-117">Install the QDK locally</span></span>

<span data-ttu-id="d7f00-118">Q# kodunu sık kullandığınız IDE’lerin çoğunda geliştirebilir, aynı zamanda Q# ile Python ve .NET (C#, F#) gibi diğer dilleri tümleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d7f00-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="d7f00-119">**VS Code<br>(2019 veya üzeri)**</span><span class="sxs-lookup"><span data-stu-id="d7f00-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="d7f00-120">**Visual Studio<br>(2019 veya üzeri)**</span><span class="sxs-lookup"><span data-stu-id="d7f00-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="d7f00-121">**Jupyter Notebooks**</span><span class="sxs-lookup"><span data-stu-id="d7f00-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="d7f00-122">**Komut satırı**</span><span class="sxs-lookup"><span data-stu-id="d7f00-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="d7f00-123">**İşletim sistemi**</span><span class="sxs-lookup"><span data-stu-id="d7f00-123">**OS**</span></span> |<span data-ttu-id="d7f00-124">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="d7f00-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="d7f00-125">Yalnızca Windows</span><span class="sxs-lookup"><span data-stu-id="d7f00-125">Windows only</span></span> |<span data-ttu-id="d7f00-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="d7f00-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="d7f00-127">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="d7f00-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="d7f00-128">**Q# tek başına**</span><span class="sxs-lookup"><span data-stu-id="d7f00-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="d7f00-129">Yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="d7f00-130">Yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="d7f00-131">Yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="d7f00-132">Yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="d7f00-133">**Q# ve Python**</span><span class="sxs-lookup"><span data-stu-id="d7f00-133">**Q#  and Python**</span></span> |[<span data-ttu-id="d7f00-134">Yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="d7f00-135">Yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="d7f00-136">Yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="d7f00-137">Yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="d7f00-138">**Q# ve .NET (C#, F#)**</span><span class="sxs-lookup"><span data-stu-id="d7f00-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="d7f00-139">Yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="d7f00-140">Yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="d7f00-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="d7f00-141">&#10006;</span></span> |[<span data-ttu-id="d7f00-142">Yükleme</span><span class="sxs-lookup"><span data-stu-id="d7f00-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="d7f00-143">QDK’yı çevrimiçi olarak kullanma</span><span class="sxs-lookup"><span data-stu-id="d7f00-143">Use the QDK Online</span></span>

<span data-ttu-id="d7f00-144">Şu seçenekler sayesinde, yerel olarak herhangi bir program yüklemeden Q# kodu geliştirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="d7f00-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="d7f00-145">Kaynak</span><span class="sxs-lookup"><span data-stu-id="d7f00-145">Resource</span></span>|<span data-ttu-id="d7f00-146">Avantajlar</span><span class="sxs-lookup"><span data-stu-id="d7f00-146">Advantages</span></span>|<span data-ttu-id="d7f00-147">Sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="d7f00-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="d7f00-148">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="d7f00-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="d7f00-149">Zengin bir çevrimiçi geliştirme ortamı</span><span class="sxs-lookup"><span data-stu-id="d7f00-149">A rich online development environment</span></span>  |<span data-ttu-id="d7f00-150">Bir Azure aboneliği ve planı gerekir</span><span class="sxs-lookup"><span data-stu-id="d7f00-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="d7f00-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="d7f00-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="d7f00-152">Ücretsiz, çevrimiçi not defteri deneyimi</span><span class="sxs-lookup"><span data-stu-id="d7f00-152">Free online notebook experience</span></span> |<span data-ttu-id="d7f00-153">Kalıcılık yok</span><span class="sxs-lookup"><span data-stu-id="d7f00-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="d7f00-154">QDK’yı Docker ile kullanma</span><span class="sxs-lookup"><span data-stu-id="d7f00-154">Use the QDK with Docker</span></span>

<span data-ttu-id="d7f00-155">QDK Docker görüntümüzü yerel Docker yüklemenizde veya ACI gibi, Docker görüntülerini destekleyen herhangi bir hizmet aracılığıyla bulutta kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d7f00-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="d7f00-156">IQ# Docker görüntüsünü https://github.com/microsoft/iqsharp/#using-iq-as-a-container sayfasından indirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d7f00-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="d7f00-157">Geliştirme ortamlarını hızla tanımlamak için Docker’ı bir Visual Studio Code Uzaktan Geliştirme Kapsayıcısı ile de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d7f00-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="d7f00-158">VS Code Geliştirme Kapsayıcıları hakkında daha fazla bilgi için bkz. https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="d7f00-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7f00-159">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="d7f00-159">Next steps</span></span>

<span data-ttu-id="d7f00-160">Bu kurulumların her birine yönelik iş akışları, [Q# programını çalıştırma yolları](xref:microsoft.quantum.guide.host-programs) konusunda açıklanmış ve karşılaştırılmıştır.</span><span class="sxs-lookup"><span data-stu-id="d7f00-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
