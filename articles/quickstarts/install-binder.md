---
title: Q# ve Binder ile geliştirme
description: Binder kullanarak Q# uygulaması oluşturmayı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f993a1145dd8c01045d4cc7cfd0c98efd574ea78
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836578"
---
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="0a11c-103">Q# ve Binder ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="0a11c-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="0a11c-104">Jupyter Not Defterlerinizi çevrimiçi olarak çalıştırıp paylaşmak için Binder’ı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0a11c-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="0a11c-105">Binder’ı Microsoft QDK örnekleri ile kullanma</span><span class="sxs-lookup"><span data-stu-id="0a11c-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="0a11c-106">Binder’ı Microsoft QDK örneklerini kullanacak şekilde otomatik olarak yapılandırmak için:</span><span class="sxs-lookup"><span data-stu-id="0a11c-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="0a11c-107">Bir tarayıcı açın ve https://aka.ms/try-qsharp uygulamasını çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="0a11c-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="0a11c-108">**Quantum geliştirme seti örnekleri** giriş sayfasında, kendi kuantum uygulama not defterlerinizi yazmak amacıyla IQ# kullanmayı öğrenmek için **Q# not defterine** tıklayın.</span><span class="sxs-lookup"><span data-stu-id="0a11c-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![QDK giriş sayfası](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="0a11c-110">Binder’ı kendi not defterlerinizle ve deponuzla kullanma</span><span class="sxs-lookup"><span data-stu-id="0a11c-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="0a11c-111">GitHub deponuzda zaten not defterleri varsa Binder’ı deponuzla çalışacak şekilde yapılandırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="0a11c-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="0a11c-112">Deponuzun kökünde *Dockerfile* adlı bir dosya olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="0a11c-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="0a11c-113">Dosyada en azından aşağıdaki satırlar bulunmalıdır:</span><span class="sxs-lookup"><span data-stu-id="0a11c-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="0a11c-114">IQ# uygulamasının en güncel sürümünü [Sürüm Notları](xref:microsoft.quantum.relnotes)’ndan doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0a11c-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="0a11c-115">Dockerfile oluşturma hakkında daha fazla bilgi için [Dockerfile başvurusuna](https://docs.docker.com/engine/reference/builder/) göz atın.</span><span class="sxs-lookup"><span data-stu-id="0a11c-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="0a11c-116">Tarayıcınızdan [mybinder.org](https://mybinder.org) sayfasını açın.</span><span class="sxs-lookup"><span data-stu-id="0a11c-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="0a11c-117">Deponuzun adını **GitHub URL**’si (örneğin *Adım/Depom*) olarak girin ve **Başlat**’a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="0a11c-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![MyBinder formu](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="0a11c-119">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="0a11c-119">Next steps</span></span>

<span data-ttu-id="0a11c-120">Binder ortamınızı ayarladığınıza göre şimdi [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0a11c-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
