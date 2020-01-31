---
title: Microsoft Quantum Development Kit (QDK) yüklemeyi öğrenin
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: b209f0b600d973c3870c66060e1b484ec519322f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820717"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="f5431-102">Microsoft Quantum Development Kit (QDK) yükleme</span><span class="sxs-lookup"><span data-stu-id="f5431-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="f5431-103">Kuantum programlamaya başlayabilmek için Microsoft Quantum Development Kit (QDK) yükleme hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="f5431-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="f5431-104">QDK aşağıdakilerden oluşur:</span><span class="sxs-lookup"><span data-stu-id="f5431-104">The QDK consists of:</span></span>

- <span data-ttu-id="f5431-105">Q# programlama dili</span><span class="sxs-lookup"><span data-stu-id="f5431-105">the Q# programming language</span></span>
- <span data-ttu-id="f5431-106">Q# dilinde karmaşık işlevleri özetleyen bir kitaplık kümesi</span><span class="sxs-lookup"><span data-stu-id="f5431-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="f5431-107">Q# dilinde yazılan kuantum programlarını çalıştırmak için Python ve .NET dilleri (ör.: C#, F# ve VB.NET) API’leri</span><span class="sxs-lookup"><span data-stu-id="f5431-107">APIs for Python and .NET languages (i.e.: C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="f5431-108">geliştirmenizi kolaylaştıracak araçlar</span><span class="sxs-lookup"><span data-stu-id="f5431-108">tools to facilitate your development</span></span>

<span data-ttu-id="f5431-109">Q# programları genellikle bir .NET dilinde (genellikle C#) veya Python ile yazılmış bir konak programla eşleştirilir.</span><span class="sxs-lookup"><span data-stu-id="f5431-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="f5431-110">Bu, klasik bir programın içinden kuantum işlemlerini çağırmamıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="f5431-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="f5431-111">Ayrıca QDK, IQ# Jupyter çekirdeğine sahip Jupyter Notebook’ları için Q# desteği sağlar.</span><span class="sxs-lookup"><span data-stu-id="f5431-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="f5431-112">QDK, birden çok geliştirme ortamında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="f5431-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="f5431-113">Aşağıdaki bölümlerde tercih ettiğiniz kurulumu seçin:</span><span class="sxs-lookup"><span data-stu-id="f5431-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="f5431-114">[C# için Q# yükleme:](xref:microsoft.quantum.install.cs) Q# işlemlerini çağıran bir C# konak programı oluşturmak için C# ile Q#’ı birleştirmek istiyorsanız bu ortamı seçin.</span><span class="sxs-lookup"><span data-stu-id="f5431-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="f5431-115">[Python için Q# yükleme:](xref:microsoft.quantum.install.python) Q# işlemlerini çağıran bir Python konak programı oluşturmak için Python ile Q#’ı birleştirmek istiyorsanız bu ortamı seçin.</span><span class="sxs-lookup"><span data-stu-id="f5431-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="f5431-116">[Jupyter Notebook’ları için Q# yükleme:](xref:microsoft.quantum.install.jupyter) Eklenmiş metin içeren hücrelerde Q# kodu yürütmek veya kuantum bilgi işlem etkileşimli öğreticileri oluşturmak istiyorsanız bu ortamı seçin.</span><span class="sxs-lookup"><span data-stu-id="f5431-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="f5431-117">Q#’ı harici bir klasik konak programıyla birleştirmek istiyorsanız bu ortamı seçmeyin.</span><span class="sxs-lookup"><span data-stu-id="f5431-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
