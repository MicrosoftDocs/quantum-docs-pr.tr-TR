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
ms.openlocfilehash: c6e128ea8b3845336fb692d2bceefda998b935d9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228857"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="e427d-103">Microsoft Quantum geliştirme setini (QDK) ayarlama</span><span class="sxs-lookup"><span data-stu-id="e427d-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="e427d-104">Kuantum programlamaya başlayabilmek amacıyla, Microsoft Quantum geliştirme setini (QDK) ortamınız için nasıl ayarlayacağınızı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="e427d-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="e427d-105">QDK aşağıdakilerden oluşur:</span><span class="sxs-lookup"><span data-stu-id="e427d-105">The QDK consists of:</span></span>

- <span data-ttu-id="e427d-106">Q# programlama dili</span><span class="sxs-lookup"><span data-stu-id="e427d-106">The Q# programming language</span></span>
- <span data-ttu-id="e427d-107">Q# dilindeki karmaşık işlevleri soyutlayan bir kitaplık seti</span><span class="sxs-lookup"><span data-stu-id="e427d-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="e427d-108">Q# dilinde yazılmış kuantum programlarını çalıştırmak için Python ve .NET dillerine (C#, F# ve VB.NET) yönelik API’ler</span><span class="sxs-lookup"><span data-stu-id="e427d-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="e427d-109">Geliştirmenizi kolaylaştıracak araçlar</span><span class="sxs-lookup"><span data-stu-id="e427d-109">Tools to facilitate your development</span></span>

<span data-ttu-id="e427d-110">Q# programları Visual Studio Code veya Visual Studio kullanarak, IQ# Jupyter çekirdeğine sahip Jupyter Not Defterleri aracılığıyla ya da Python veya .NET dilinde (C#, F#) yazılmış bir konak ortamıyla eşlenmiş bağımsız uygulamalar olarak çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="e427d-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="e427d-111">Q# programlarını [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) veya [Docker](#use-the-qdk-with-docker) kullanarak da çevrimiçi olarak çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e427d-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="e427d-112">QDK’yı ayarlama seçenekleri</span><span class="sxs-lookup"><span data-stu-id="e427d-112">Options for setting up the QDK</span></span>

<span data-ttu-id="e427d-113">QDK’yı üç şekilde kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="e427d-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="e427d-114">QDK’yı yerel olarak yükleyerek</span><span class="sxs-lookup"><span data-stu-id="e427d-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="e427d-115">QDK’yı çevrimiçi olarak kullanarak</span><span class="sxs-lookup"><span data-stu-id="e427d-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="e427d-116">QDK Docker görüntüsü kullanarak</span><span class="sxs-lookup"><span data-stu-id="e427d-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="e427d-117">QDK’yı yerel olarak yükleme</span><span class="sxs-lookup"><span data-stu-id="e427d-117">Install the QDK locally</span></span>

<span data-ttu-id="e427d-118">Q# kodunu sık kullandığınız IDE’lerin çoğunda geliştirebilir, aynı zamanda Q# ile Python ve .NET (C#, F#) gibi diğer dilleri tümleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e427d-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="e427d-119"><b>VS Code</span><span class="sxs-lookup"><span data-stu-id="e427d-119"><b>VS Code</span></span><br><span data-ttu-id="e427d-120">(2019 veya üzeri)</b></span><span class="sxs-lookup"><span data-stu-id="e427d-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="e427d-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e427d-121"><b>Visual Studio</span></span><br><span data-ttu-id="e427d-122">(2019 veya üzeri)</b></span><span class="sxs-lookup"><span data-stu-id="e427d-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="e427d-123"><b>Jupyter Notebooks</b></span><span class="sxs-lookup"><span data-stu-id="e427d-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="e427d-124"><b>Komut satırı</b></span><span class="sxs-lookup"><span data-stu-id="e427d-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="e427d-125"><b>İşletim sistemi desteği:</b></span><span class="sxs-lookup"><span data-stu-id="e427d-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="e427d-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="e427d-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="e427d-127">Yalnızca Windows</span><span class="sxs-lookup"><span data-stu-id="e427d-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="e427d-128">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="e427d-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="e427d-129">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="e427d-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="e427d-130"><b>Q# tek başına</b></span><span class="sxs-lookup"><span data-stu-id="e427d-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="e427d-131"><a href="xref:microsoft.quantum.install.standalone">Yükleme</a></span><span class="sxs-lookup"><span data-stu-id="e427d-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e427d-132"><a href="xref:microsoft.quantum.install.standalone">Yükleme</a></span><span class="sxs-lookup"><span data-stu-id="e427d-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e427d-133"><a href="xref:microsoft.quantum.install.jupyter">Yükleme</a></span><span class="sxs-lookup"><span data-stu-id="e427d-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e427d-134"><a href="xref:microsoft.quantum.install.standalone">Yükleme</a></span><span class="sxs-lookup"><span data-stu-id="e427d-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="e427d-135"><b>Q# ve Python</b></span><span class="sxs-lookup"><span data-stu-id="e427d-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="e427d-136"><a href="xref:microsoft.quantum.install.python">Yükleme</a></span><span class="sxs-lookup"><span data-stu-id="e427d-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e427d-137"><a href="xref:microsoft.quantum.install.python">Yükleme</a></span><span class="sxs-lookup"><span data-stu-id="e427d-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e427d-138"><a href="xref:microsoft.quantum.install.python">Yükleme</a></span><span class="sxs-lookup"><span data-stu-id="e427d-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e427d-139"><a href="xref:microsoft.quantum.install.python">Yükleme</a></span><span class="sxs-lookup"><span data-stu-id="e427d-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="e427d-140"><b>Q# ve .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="e427d-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="e427d-141"><a href="xref:microsoft.quantum.install.cs">Yükleme</a></span><span class="sxs-lookup"><span data-stu-id="e427d-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e427d-142"><a href="xref:microsoft.quantum.install.cs">Yükleme</a></span><span class="sxs-lookup"><span data-stu-id="e427d-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="e427d-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="e427d-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="e427d-144"><a href="xref:microsoft.quantum.install.cs">Yükleme</a></span><span class="sxs-lookup"><span data-stu-id="e427d-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="e427d-145">QDK’yı çevrimiçi olarak kullanma</span><span class="sxs-lookup"><span data-stu-id="e427d-145">Use the QDK Online</span></span>

<span data-ttu-id="e427d-146">Şu seçenekler sayesinde, yerel olarak herhangi bir program yüklemeden Q# kodu geliştirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="e427d-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="e427d-147">Kaynak</span><span class="sxs-lookup"><span data-stu-id="e427d-147">Resource</span></span>|<span data-ttu-id="e427d-148">Avantajlar</span><span class="sxs-lookup"><span data-stu-id="e427d-148">Advantages</span></span>|<span data-ttu-id="e427d-149">Sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="e427d-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="e427d-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="e427d-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="e427d-151">Zengin bir çevrimiçi geliştirme ortamı</span><span class="sxs-lookup"><span data-stu-id="e427d-151">A rich online development environment</span></span>  |<span data-ttu-id="e427d-152">Bir Azure aboneliği ve planı gerekir</span><span class="sxs-lookup"><span data-stu-id="e427d-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="e427d-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="e427d-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="e427d-154">Ücretsiz, çevrimiçi not defteri deneyimi</span><span class="sxs-lookup"><span data-stu-id="e427d-154">Free online notebook experience</span></span> |<span data-ttu-id="e427d-155">Kalıcılık yok</span><span class="sxs-lookup"><span data-stu-id="e427d-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="e427d-156">QDK’yı Docker ile kullanma</span><span class="sxs-lookup"><span data-stu-id="e427d-156">Use the QDK with Docker</span></span>

<span data-ttu-id="e427d-157">QDK Docker görüntümüzü yerel Docker yüklemenizde veya ACI gibi, Docker görüntülerini destekleyen herhangi bir hizmet aracılığıyla bulutta kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e427d-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="e427d-158">IQ# Docker görüntüsünü https://github.com/microsoft/iqsharp/#using-iq-as-a-container sayfasından indirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e427d-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="e427d-159">Geliştirme ortamlarını hızla tanımlamak için Docker’ı bir Visual Studio Code Uzaktan Geliştirme Kapsayıcısı ile de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e427d-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="e427d-160">VS Code Geliştirme Kapsayıcıları hakkında daha fazla bilgi için bkz. https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="e427d-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e427d-161">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="e427d-161">Next steps</span></span>

<span data-ttu-id="e427d-162">Bu kurulumların her birine yönelik iş akışları, [Q# programını çalıştırma yolları](xref:microsoft.quantum.guide.host-programs) konusunda açıklanmış ve karşılaştırılmıştır.</span><span class="sxs-lookup"><span data-stu-id="e427d-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
