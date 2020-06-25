---
title: Çekme istekleri açılıyor
description: Microsoft Quantum Development Kit kod veya belge katkıda bulunmak için hazırsanız GitHub çekme isteği göndermeyi öğrenin.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: 82af3b5123588cc06882f746ffcb0402ad3f0f2e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275472"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="f4154-103">Çekme İsteklerini Açma</span><span class="sxs-lookup"><span data-stu-id="f4154-103">Opening Pull Requests</span></span> #

<span data-ttu-id="f4154-104">Hisse geliştirme kiti için tüm belgeler, GitHub 'da barındırılan birkaç depo kullanılarak git sürüm denetim sistemi kullanılarak yönetilir.</span><span class="sxs-lookup"><span data-stu-id="f4154-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="f4154-105">Git ve GitHub 'ın birlikte kullanılması, hisse geliştirme setinde büyük ölçüde işbirliği yapmayı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="f4154-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="f4154-106">Özellikle, bu deponun tamamen bağımsız bir kopyasını oluşturmak için herhangi bir git deposu kopyalanabilir veya eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="f4154-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="f4154-107">Bu, araçlarla ve tercih ettiğiniz bir hızda katkılarınız üzerinde çalışmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="f4154-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="f4154-108">Hazırsanız, GitHub 'ın _çekme isteği_ işlevselliğini kullanarak katkılarımıza katkılarınızı dahil etmek için bize bir istek gönderebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f4154-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="f4154-109">Her çekme isteğinin sayfasında katkılarınızı oluşturan tüm değişikliklerin ayrıntıları, katkılarınız üzerinde bir açıklama listesi ve topluluğun diğer üyelerinin geri bildirim ve öneri sağlamak için kullanabileceği bir gözden geçirme araçları bulunur.</span><span class="sxs-lookup"><span data-stu-id="f4154-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="f4154-110">Git ile ilgili bir tam öğretici bu kılavuzun kapsamı dışındadır, ancak öğrenme git hakkında daha fazla kaynak için aşağıdaki bağlantıları önerebiliriz:</span><span class="sxs-lookup"><span data-stu-id="f4154-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="f4154-111">[Git hakkında bilgi edinin](https://www.atlassian.com/git): atlasme 'Den bir git öğreticileri kümesi.</span><span class="sxs-lookup"><span data-stu-id="f4154-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="f4154-112">[Visual Studio Code sürüm denetimi](https://code.visualstudio.com/docs/editor/versioncontrol): GIT için guı olarak Visual Studio Code kullanma kılavuzu.</span><span class="sxs-lookup"><span data-stu-id="f4154-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="f4154-113">[GitHub Öğrenme Laboratuvarı](https://lab.github.com/): git, GitHub ve ilgili teknolojileri kullanmaya yönelik çevrimiçi kurslar kümesi.</span><span class="sxs-lookup"><span data-stu-id="f4154-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="f4154-114">[Git görselleştirme](https://git-school.github.io/visualizing-git/): git komutlarının bir deponun durumunu nasıl değiştirmelerini görselleştirmede etkileşimli bir araç.</span><span class="sxs-lookup"><span data-stu-id="f4154-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="f4154-115">[Git Ile sürüm denetimi (EPQSıS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): bilimsel bilgi işlem doğrultusunda bir git öğreticisi.</span><span class="sxs-lookup"><span data-stu-id="f4154-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="f4154-116">[Git dallandırmayı öğrenin](https://learngitbranching.js.org/): yeni git özellikleri hakkında bilgi edinmek için etkileşimli bir dallanma kümesi ve yeniden temellendirme bulmaca vs.</span><span class="sxs-lookup"><span data-stu-id="f4154-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="f4154-117">Çekme Isteği nedir?</span><span class="sxs-lookup"><span data-stu-id="f4154-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="f4154-118">Yukarıdakileri söylediğinizde, bir çekme isteğinin ne **olduğunu**söylemek için birkaç dakika sürer.</span><span class="sxs-lookup"><span data-stu-id="f4154-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="f4154-119">Git ile çalışırken tüm değişiklikler, bu değişikliklerin, bu değişikliklerden önce deponun durumuyla nasıl ilişkili olduğunu betimleyen _işlemeler_ olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="f4154-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="f4154-120">Genellikle yürütmelerin, önceki işlemelerden oklarla daireler olarak çizildiğini gösteren diyagramlar çizeceğiz.</span><span class="sxs-lookup"><span data-stu-id="f4154-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="f4154-121">Adlı _dalda_ bir katkı başladığınızı varsayalım `feature` .</span><span class="sxs-lookup"><span data-stu-id="f4154-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="f4154-122">Bundan sonra **Microsoft/hisse** 'ın çatalınız şuna benzeyebilir:</span><span class="sxs-lookup"><span data-stu-id="f4154-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![GitHub 'da çalışma dalı](~/media/git-workflow-step0.png)

<span data-ttu-id="f4154-124">Değişikliklerinizi yerel deponuzda yaparsanız, yukarı akış meydana gelen değişikliklere göre yakalamak için başka bir depodan yaptığınız değişiklikleri sizinkilerle _çekebilirsiniz_ .</span><span class="sxs-lookup"><span data-stu-id="f4154-124">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![Yukarı akış deposundan değişiklikleri çekme ve birleştirme](~/media/git-workflow-step1.png)

<span data-ttu-id="f4154-126">Çekme istekleri aynı şekilde çalışır, ancak ters: bir çekme isteği açtığınızda, yukarı akış deposunun katkılarınızı çekmesini isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f4154-126">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![Değişikliklerinizi özgün depoya geri çekmek istiyor](~/media/git-workflow-step2.png)

<span data-ttu-id="f4154-128">Depolarımızdan birine bir çekme isteği açtığınızda, GitHub, topluluklardaki başkalarının değişikliklerinizin bir özetini görmesini, bunlara yorum yapmasını ve daha da iyi bir katkı sunmanın yanı sıra yardımcı olma önerileri yapmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="f4154-128">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![GitHub 'da çekme isteğinin ekran görüntüsü](~/media/pull-request-header.png)

<span data-ttu-id="f4154-130">Bu işlemi kullanmak, katkılarını geliştirmek ve hisse programlama topluluğu için yüksek kaliteli bir ürünü sürdürmek amacıyla GitHub işlevlerini kullanmamıza yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="f4154-130">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="f4154-131">Çekme Isteği oluşturma</span><span class="sxs-lookup"><span data-stu-id="f4154-131">How to Make a Pull Request</span></span> ##

<span data-ttu-id="f4154-132">Çekme isteği oluşturmak için iki ana yol vardır.</span><span class="sxs-lookup"><span data-stu-id="f4154-132">There are two main ways to make a pull request.</span></span>  
<span data-ttu-id="f4154-133">Yalnızca tek bir dosyayı etkileyen küçük değişiklikler için GitHub Web arabirimi, çekme isteğini tamamen çevrimiçi hale getirmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="f4154-133">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span> <span data-ttu-id="f4154-134">Düzenlemek istediğiniz dosyaya gitmeniz ve düzenleme simgesini kullanmanız yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="f4154-134">Simply navigate to the file you want to edit and use the edit icon.</span></span>  
<span data-ttu-id="f4154-135">Daha karmaşık katkılar için, önce bir çekme isteğine hazırlanmak üzere depoyu yerel bilgisayarınıza klonlamak daha kolay olur.</span><span class="sxs-lookup"><span data-stu-id="f4154-135">For more complicated contributions, it's most often easier to clone the repository to your local computer to prepare for a pull request first.</span></span>

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a><span data-ttu-id="f4154-136">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="f4154-136">Next steps</span></span> ##

<span data-ttu-id="f4154-137">GIT geliştirme seti topluluğu 'na yardımcı olmak için git kullanma hakkında Tebrikler!</span><span class="sxs-lookup"><span data-stu-id="f4154-137">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="f4154-138">Kodun nasıl katkıda bulunduğu hakkında daha fazla bilgi edinmek için lütfen aşağıdaki kılavuzla devam edin.</span><span class="sxs-lookup"><span data-stu-id="f4154-138">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f4154-139">Kod katkıda bulunma hakkında bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="f4154-139">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
