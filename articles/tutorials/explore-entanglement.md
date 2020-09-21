---
title: Entanglement 'i ile keşfet Q#
description: "' De bir hisse programı yazmayı öğrenin Q# . Quantum Development Kit'i (QDK) kullanarak Bell Durumu uygulaması geliştirme"
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6fd7494d341a83a1354d23a283d21a7ae535e49f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834032"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="8ec52-104">Öğretici: Q\# ile dolaşıklığı keşfetme</span><span class="sxs-lookup"><span data-stu-id="8ec52-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="8ec52-105">Bu öğreticide, Q# qubits 'i işleyen ve ölçtüğünden ve üst konum ve entanglement 'in etkilerini gösteren bir programı nasıl yazacağınız gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>

<span data-ttu-id="8ec52-106">Kuantum dolaşıklığı göstermek için Bell adında bir uygulama yazacaksınız.</span><span class="sxs-lookup"><span data-stu-id="8ec52-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="8ec52-107">Bell adı, en basit süper konum ve kuantum dolaşıklığı örneklerini göstermek için kullanılan iki kubitin belirli kuantum durumları olan Bell durumlarını ifade eder.</span><span class="sxs-lookup"><span data-stu-id="8ec52-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="8ec52-108">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="8ec52-108">Pre-requisites</span></span>

<span data-ttu-id="8ec52-109">Kodlamaya başlamaya hazırsanız devam etmeden önce şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="8ec52-109">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="8ec52-110">[Install](xref:microsoft.quantum.install) Tercih ettiğiniz dil ve geliştirme ortamınızı kullanarak hisse geliştirme setini kullanın.</span><span class="sxs-lookup"><span data-stu-id="8ec52-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span>
* <span data-ttu-id="8ec52-111">Makinenizde QDK zaten yüklüyse en son sürüme [güncelleştirdiğinizden](xref:microsoft.quantum.update) emin olun</span><span class="sxs-lookup"><span data-stu-id="8ec52-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="8ec52-112">Ayrıca, QDK 'yi yüklemeden anlatıcı olarak, programlama dilinin genel bakışlarını Q# ve hisse bilgi işlem kavramlarının ilk kavramlarını gözden geçirerek da izleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8ec52-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="8ec52-113">Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:</span><span class="sxs-lookup"><span data-stu-id="8ec52-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="8ec52-114">Q 'da işlem oluşturma ve birleştirme\#</span><span class="sxs-lookup"><span data-stu-id="8ec52-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="8ec52-115">Qubits 'i üst konuma yerleştirmek için işlemler oluşturun, bunları zenginedin ve ölçün.</span><span class="sxs-lookup"><span data-stu-id="8ec52-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="8ec52-116">Bir benzeticide çalıştırılan bir programla hisse entanglement 'i gösterir Q# .</span><span class="sxs-lookup"><span data-stu-id="8ec52-116">Demonstrate quantum entanglement with a Q# program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="8ec52-117">QDK ile qubit davranışı gösterme</span><span class="sxs-lookup"><span data-stu-id="8ec52-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="8ec52-118">Klasik bitler 0 veya 1 gibi tek bir ikili değeri barındırırken, [kubitin](xref:microsoft.quantum.glossary#qubit) durumu 0 ve 1’in bir **süper konumunda** olabilir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="8ec52-119">Kavramsal olarak, bir qubit durumu soyut bir alanda (vektör olarak da bilinir) bir yön olarak düşünülebilir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="8ec52-120">Bir qubit durumu olası yönlere ait olabilir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="8ec52-121">İki **klasik durum**, iki yöndür. Bu da %100 oranında 0 ölçme şansını ve %100 oranında 1 ölçme şansını gösterir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="8ec52-122">Ölçüm işlemi ikili sonuç üretir ve bir kubit durumunu değiştirir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="8ec52-123">Ölçüm, 0 veya 1 olan bir ikili değer üretir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="8ec52-124">Kubit, süper konumdan (herhangi bir yöne) klasik durumlardan birine geçer.</span><span class="sxs-lookup"><span data-stu-id="8ec52-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="8ec52-125">Bundan sonra aynı ölçümün başka bir işlemle müdahale edilmeden yinelenmesi durumunda aynı ikili sonuç ortaya çıkar.</span><span class="sxs-lookup"><span data-stu-id="8ec52-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="8ec52-126">Birden çok kubit [**dolaşık hale getirilebilir**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="8ec52-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="8ec52-127">Dolaşık bir kubitin ölçümünü yaptığınızda, diğerinin durumuna ilişkin bilginiz de güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="8ec52-128">Şimdi bu davranışın nasıl ifade ettireceğiz gösterilmektedir Q# .</span><span class="sxs-lookup"><span data-stu-id="8ec52-128">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="8ec52-129">Mümkün olan en basit programla başlayıp kuantum süper konumu ile kuantum dolaşıklığını göstermek için bunu geliştirirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8ec52-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-no-locq-project"></a><span data-ttu-id="8ec52-130">Proje oluşturma Q#</span><span class="sxs-lookup"><span data-stu-id="8ec52-130">Creating a Q# project</span></span>

<span data-ttu-id="8ec52-131">Yapmanız gereken ilk şey yeni bir Q# Proje oluşturmaktır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-131">The first thing we have to do is to create a new Q# project.</span></span> <span data-ttu-id="8ec52-132">Bu öğreticide, [ Q# vs Code olan uygulamalara](xref:microsoft.quantum.install.standalone)göre ortamı kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="8ec52-132">In this tutorial we are going to use the environment based on [Q# applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="8ec52-133">Yeni bir proje oluşturmak için VS Code:</span><span class="sxs-lookup"><span data-stu-id="8ec52-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="8ec52-134">**Görünüm** -> **Komut Paleti**’ne tıklayın ve **Q#: Yeni Proje Oluştur**’u seçin.</span><span class="sxs-lookup"><span data-stu-id="8ec52-134">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="8ec52-135">**Bağımsız konsol uygulaması**’na tıklayın.</span><span class="sxs-lookup"><span data-stu-id="8ec52-135">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="8ec52-136">Projenin kaydedileceği konuma gidin ve **Proje Oluştur**’a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="8ec52-136">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="8ec52-137">Proje başarıyla oluşturulduğunda, sağ alt kısımdaki **Yeni proje aç...** seçeneğine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="8ec52-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="8ec52-138">Bu durumda proje çağırılır `Bell` .</span><span class="sxs-lookup"><span data-stu-id="8ec52-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="8ec52-139">Bu iki dosya oluşturur: `Bell.csproj` , proje dosyası ve `Program.qs` Q# uygulamamızı yazmak için kullandığımız bir uygulamanın şablonu.</span><span class="sxs-lookup"><span data-stu-id="8ec52-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a Q# application that we will use to write our application.</span></span> <span data-ttu-id="8ec52-140">İçeriği şu `Program.qs` olmalıdır:</span><span class="sxs-lookup"><span data-stu-id="8ec52-140">The content of `Program.qs` should be:</span></span>

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a><span data-ttu-id="8ec52-141">Q uygulamasını yazma \#</span><span class="sxs-lookup"><span data-stu-id="8ec52-141">Write the Q\# application</span></span>
 
<span data-ttu-id="8ec52-142">Bizim amamız, belirli bir hisse durumunda iki qubit hazırlanmaktır. Bu durumda, Q# eyaletlerin durumunu değiştirmek ve üst konum ve entanglement 'in etkilerini göstermek için ile qubit üzerinde nasıl çalışılacağı gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="8ec52-143">Bu parçaları, qubit durumları, işlemleri ve ölçümü tanıtmak için bir parça oluşturacak şekilde oluşturacağız.</span><span class="sxs-lookup"><span data-stu-id="8ec52-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="8ec52-144">Ölçüyü kullanarak qubit Başlat</span><span class="sxs-lookup"><span data-stu-id="8ec52-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="8ec52-145">Aşağıdaki ilk kodda, ' de qubits ile nasıl çalışacağız gösterilmektedir Q# .</span><span class="sxs-lookup"><span data-stu-id="8ec52-145">In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="8ec52-146">İki işlem tanıtıyoruz [`M`](xref:microsoft.quantum.intrinsic.m) ve [`X`](xref:microsoft.quantum.intrinsic.x) bir qubit durumunu dönüştürecek.</span><span class="sxs-lookup"><span data-stu-id="8ec52-146">We’ll introduce two operations, [`M`](xref:microsoft.quantum.intrinsic.m) and [`X`](xref:microsoft.quantum.intrinsic.x) that transform the state of a qubit.</span></span> <span data-ttu-id="8ec52-147">Bu kod parçacığında parametre olarak bir kubit ile kubitin içinde bulunmasını istediğimiz durumu temsil eden `desired` parametresini alan `SetQubitState` işlemi tanımlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="8ec52-148">`SetQubitState` işlemi, `M` işlemini kullanarak kubit üzerinde bir ölçüm gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="8ec52-149">Q#' De, bir qubit ölçümü her zaman `Zero` ya da döndürür `One` .</span><span class="sxs-lookup"><span data-stu-id="8ec52-149">In Q#, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="8ec52-150">Ölçüm, istenen değere eşit olmayan bir değer döndürürse, `SetQubitState` "qubit" değerini çevirir; diğer bir deyişle, bir işlem çalıştırır ve bu, `X` qubit durumunu döndürülen ve geri çevrilen bir ölçünün olasılıkların ne olduğu yeni bir duruma geçirir `Zero` `One` .</span><span class="sxs-lookup"><span data-stu-id="8ec52-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it runs an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="8ec52-151">Bu şekilde, `SetQubitState` her zaman hedef qubit 'i istenen duruma geçirir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="8ec52-152">İçeriğini `Program.qs` aşağıdaki kodla değiştirin:</span><span class="sxs-lookup"><span data-stu-id="8ec52-152">Replace the contents of `Program.qs` with the following code:</span></span>


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

<span data-ttu-id="8ec52-153">Bu işlem artık kubiti klasik bir duruma getirerek %100 `Zero` veya %100 `One` döndürmesi sağlanabilir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="8ec52-154">`Zero` ve `One`, bir kubit ölçümünün mümkün olan iki sonucunu gösteren sabitlerdir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="8ec52-155">`SetQubitState` işlemi kubiti ölçer.</span><span class="sxs-lookup"><span data-stu-id="8ec52-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="8ec52-156">Qubit, istediğimiz durumdaysa, `SetQubitState` bunu tek başına bırakır; Aksi takdirde, `X` işlemi çalıştırarak qubit durumunu istenen duruma göre değiştirirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8ec52-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by running the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-no-locq-operations"></a><span data-ttu-id="8ec52-157">Q#İşlemler hakkında</span><span class="sxs-lookup"><span data-stu-id="8ec52-157">About Q# operations</span></span>

<span data-ttu-id="8ec52-158">Q#İşlem bir hisse alt yordamı.</span><span class="sxs-lookup"><span data-stu-id="8ec52-158">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="8ec52-159">Diğer bir deyişle, diğer hisse işleme çağrıları içeren çağrılabilir bir yordamdır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="8ec52-160">İşlemin bağımsız değişkenleri parantez içinde tanımlama grubu olarak belirtilir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="8ec52-161">Bir iki nokta işareti eklendikten sonra işlemin dönüş türü belirtilir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="8ec52-162">Bu örnekte `SetQubitState` işleminin dönüşü yoktur, dolayısıyla `Unit` döndürüyor olarak işaret edilir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-162">In this case, the `SetQubitState` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="8ec52-163">Bu, Q# C# ' de `unit` kabaca benzer olan `void` ve Python 'da boş bir tanımlama grubu olan ( `()` tür Ipucuyla temsil edilen) F # ' ın eşdeğeridir `Tuple[()]` .</span><span class="sxs-lookup"><span data-stu-id="8ec52-163">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple in Python (`()`, represented by the type hint `Tuple[()]`).</span></span>

<span data-ttu-id="8ec52-164">İlk işlem sırasında iki hisse işlem kullandınız Q# :</span><span class="sxs-lookup"><span data-stu-id="8ec52-164">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="8ec52-165">[`M`](xref:microsoft.quantum.intrinsic.m)Qubit durumunu ölçen işlem</span><span class="sxs-lookup"><span data-stu-id="8ec52-165">The [`M`](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="8ec52-166">[`X`](xref:microsoft.quantum.intrinsic.x)Bir qubit durumunu ters döndüren işlem</span><span class="sxs-lookup"><span data-stu-id="8ec52-166">The [`X`](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="8ec52-167">Kuantum işlemi, kubitin durumunu dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="8ec52-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="8ec52-168">Bazen kuantum işlemleri, klasik mantıksal geçitlere benzetildiğinden geçit olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="8ec52-169">Bu kullanım kuantum bilgisayarların ilk dönemlerine dayanır. Bu dönemde algoritmaların yalnızca teorik yapılardı ve klasik bilgi işlem devre şemalarına benzer şekilde görselleştirilirdi.</span><span class="sxs-lookup"><span data-stu-id="8ec52-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="8ec52-170">Ölçüm sonuçlarını sayma</span><span class="sxs-lookup"><span data-stu-id="8ec52-170">Counting measurement outcomes</span></span>

<span data-ttu-id="8ec52-171">Sonrasında `SetQubitState` işleminin etkisini göstermek için bir `TestBellState` işlemi eklenir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="8ec52-172">Bu işlem giriş olarak `Zero` veya `One` alır. Ardından `SetQubitState` işlemini bu girişle birkaç kez çağırıp kubitin ölçümünden döndürülen `Zero` sayısı ile döndürülen `One` sayısını hesaplar.</span><span class="sxs-lookup"><span data-stu-id="8ec52-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="8ec52-173">Elbette bu ilk `TestBellState` işlemi simülasyonunda çıkışın parametre girişi `Zero` döndüreceğinden, tüm kubit ölçümlerinin `Zero` ile ayarlanmış olduğunu ve parametre girişi `One` döndüreceğinden tüm kubit ölçümlerinin `One` ile ayarlanmış olduğunu göstermesi beklenir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="8ec52-174">Ayrıca, `TestBellState` üst konumu ve entanglement 'i göstermek için öğesine kod ekleyeceğiz.</span><span class="sxs-lookup"><span data-stu-id="8ec52-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="8ec52-175">Aşağıdaki işlemi `Program.qs` dosyasında ad alanının içine, `SetQubitState` işleminin sonuna ekleyin:</span><span class="sxs-lookup"><span data-stu-id="8ec52-175">Add the following operation to the `Program.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
<span data-ttu-id="8ec52-176">`return`( `Message` ) () [Microsoft. hisse. iç. ileti] işleviyle konsolda açıklayıcı bir ileti yazdırmak için önce bir satır ekledik.</span><span class="sxs-lookup"><span data-stu-id="8ec52-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="8ec52-177">Bu işlem (`TestBellState`) `count` yinelemeleri için döngü yapar, bir kubitte belirtilen `initial` değerini ayarlar ve ardından sonucu ölçer (`M`).</span><span class="sxs-lookup"><span data-stu-id="8ec52-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="8ec52-178">Kaç sıfır ve bir ölçtüğümüzle ilgili istatistikleri toplar ve bunları çağrıyı yapana döndürür.</span><span class="sxs-lookup"><span data-stu-id="8ec52-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="8ec52-179">Bir gerekli işlem daha gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-179">It performs one other necessary operation.</span></span> <span data-ttu-id="8ec52-180">Kubiti döndürmeden önce bilinen bir duruma (`Zero`) sıfırlayarak diğerlerinin bu kubiti bilinen durumda ayırmasına olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="8ec52-181">Bu, `using` deyimi için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="8ec52-182">Q içindeki değişkenler hakkında\#</span><span class="sxs-lookup"><span data-stu-id="8ec52-182">About variables in Q\#</span></span>

<span data-ttu-id="8ec52-183">Varsayılan olarak, ' deki değişkenler Q# sabittir; bu değerler bağlandıktan sonra değiştirilemez.</span><span class="sxs-lookup"><span data-stu-id="8ec52-183">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="8ec52-184">Sabit bir değişkenin bağlamasını göstermek için `let` anahtar sözcüğü kullanılır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="8ec52-185">İşlem bağımsız değişkenleri her zaman sabittir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="8ec52-186">Değeri değişebilen `numOnes` gibi bir değişkene ihtiyacınız varsa değişkeni `mutable` anahtar sözcüğüyle bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8ec52-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="8ec52-187">Değişebilir değişkenin değeri `setQubitState` deyimi kullanılarak değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-187">A mutable variable's value may be changed using a `setQubitState` statement.</span></span>

<span data-ttu-id="8ec52-188">Her iki durumda da, değişkenin türü derleyici tarafından çıkarsanır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="8ec52-189">Q# değişkenler için herhangi bir tür ek açıklaması gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="8ec52-189">Q# doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="8ec52-190">`using`Q içindeki deyimler hakkında\#</span><span class="sxs-lookup"><span data-stu-id="8ec52-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="8ec52-191">`using`İfade için de özeldir Q# .</span><span class="sxs-lookup"><span data-stu-id="8ec52-191">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="8ec52-192">Kubitleri bir kod bloğunda kullanım amacıyla ayırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="8ec52-193">' De Q# , tüm qubits, karmaşık bir algoritmanın tüm kullanım ömrü boyunca yer alan sabit kaynaklar yerine dinamik olarak ayrılır ve serbest bırakılır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-193">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="8ec52-194">Başlangıçta `using` deyimi bir kubit kümesi ayırır ve bloğun sonunda bu kubitleri serbest bırakır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="run-the-code-from-the-command-prompt"></a><span data-ttu-id="8ec52-195">Komut isteminden kodu çalıştırma</span><span class="sxs-lookup"><span data-stu-id="8ec52-195">Run the code from the command prompt</span></span>

<span data-ttu-id="8ec52-196">Kodu çalıştırmak için, komutunu sağlamamız durumunda, çağrılabilir olarak çalıştırılabilir *olan* derleyiciyi belirtmemiz gerekir `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="8ec52-196">In order to run the code we need to specify the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="8ec52-197">Bu, Q# `@EntryPoint()` çağrılabilir: `TestBellState` Bu durumda işlem tarafından doğrudan bir satır eklenerek, dosyada basit bir değişiklik ile yapılır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-197">This is done with a simple change in the Q# file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="8ec52-198">Tam kod şu şekilde olmalıdır:</span><span class="sxs-lookup"><span data-stu-id="8ec52-198">The full code should be:</span></span>

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

<span data-ttu-id="8ec52-199">Programı çalıştırmak için `count` `initial` komut isteminden ve bağımsız değişkenleri belirtmemiz gerekir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-199">To run the program we need to specify `count` and `initial` arguments from the command prompt.</span></span> <span data-ttu-id="8ec52-200">Örneğin `count = 1000` , ve ' i seçelim `initial = One` .</span><span class="sxs-lookup"><span data-stu-id="8ec52-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="8ec52-201">Aşağıdaki komutu girin:</span><span class="sxs-lookup"><span data-stu-id="8ec52-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="8ec52-202">Aşağıdaki çıktıyı gözlemleymelisiniz:</span><span class="sxs-lookup"><span data-stu-id="8ec52-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="8ec52-203">İle çalışırsanız şunu `initial = Zero` gözlemleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="8ec52-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="8ec52-204">Süper konumu hazırlama</span><span class="sxs-lookup"><span data-stu-id="8ec52-204">Prepare superposition</span></span>

<span data-ttu-id="8ec52-205">Şimdi Q# de bilgeler 'yi üst konuma yerleştirmek için nasıl ifade etmenin nasıl olduğunu inceleyelim.</span><span class="sxs-lookup"><span data-stu-id="8ec52-205">Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="8ec52-206">Hatırlayacağınız gibi bir kubit 0 ve 1 süper konumlarında olabilir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="8ec52-207">Bunu gerçekleştirmek için `Hadamard` işlemini kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="8ec52-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="8ec52-208">Kubitin klasik durumlardan birine olması halinde (ölçümün her zaman `Zero` veya her zaman `One` döndürmesi durumunda) `Hadamard` ya da `H` işlemi kubiti ölçümün %50 oranında `Zero` ve %50 oranında `One` döndüreceği bir duruma alır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="8ec52-209">Kavramsal olarak kubitin `Zero` ile `One` arasındaki bir noktada olduğu düşünülebilir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="8ec52-210">Şimdi `TestBellState` işleminin simülasyonunu yaptığımızda, ölçüm sonrasında elde edilen sonuçların `Zero` ve `One` için yaklaşık olarak eşit değerler verdiğini göreceğiz.</span><span class="sxs-lookup"><span data-stu-id="8ec52-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="8ec52-211">`X` qubit durumunu çevirir</span><span class="sxs-lookup"><span data-stu-id="8ec52-211">`X` flips qubit state</span></span>

<span data-ttu-id="8ec52-212">İlk olarak kubiti çevirmeyi deneyeceğiz. (Kubit `Zero` durumundaysa `One` durumuna çevireceğiz veya aksi halde işlemin tam tersini yapacağız.)</span><span class="sxs-lookup"><span data-stu-id="8ec52-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="8ec52-213">Bu, kubiti `TestBellState` işleminde ölçmeden önce bir `X` işlemi gerçekleştirilerek yapılır:</span><span class="sxs-lookup"><span data-stu-id="8ec52-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="8ec52-214">Sonuçlar artık tersine çevrilir:</span><span class="sxs-lookup"><span data-stu-id="8ec52-214">Now the results are reversed:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="8ec52-215">Şimdi qubits 'in hisse özelliklerini keşfedelim.</span><span class="sxs-lookup"><span data-stu-id="8ec52-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="8ec52-216">`H` üst konumu hazırlar</span><span class="sxs-lookup"><span data-stu-id="8ec52-216">`H` prepares superposition</span></span>

<span data-ttu-id="8ec52-217">Önceki çalıştırmadaki `X` işlemini bir `H` veya Hadamard işlemiyle değiştirmemiz yeterli olacaktır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="8ec52-218">Kubiti 0'dan 1'e kadar tümüyle çevirmek yerine yalnızca yarı yola kadar çevireceğiz.</span><span class="sxs-lookup"><span data-stu-id="8ec52-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="8ec52-219">`TestBellState` işleminde değiştirilen satırlar şöyle görünür:</span><span class="sxs-lookup"><span data-stu-id="8ec52-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="8ec52-220">Daha ilginç sonuçlar görülmeye başlar:</span><span class="sxs-lookup"><span data-stu-id="8ec52-220">Now the results get more interesting:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

<span data-ttu-id="8ec52-221">Her ölçtüğümüzde klasik bir değer bekleriz ama kubit 0 ile 1 arasında yarı yoldadır, dolayısıyla (istatistiksel olarak) ölçülerin yarısında 0 ve yarısında da 1 elde ederiz.</span><span class="sxs-lookup"><span data-stu-id="8ec52-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="8ec52-222">Bu **süper konum** olarak bilinir ve bize kuantum durumunun ilk gerçek görünümünü verir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="8ec52-223">Dolaşıklığı hazırlama</span><span class="sxs-lookup"><span data-stu-id="8ec52-223">Prepare entanglement</span></span>

<span data-ttu-id="8ec52-224">Şimdi de Q# qubits 'e nasıl ifade vertığınızın yollarını inceleyelim.</span><span class="sxs-lookup"><span data-stu-id="8ec52-224">Now let’s look at how Q# expresses ways to entangle qubits.</span></span>
<span data-ttu-id="8ec52-225">İlk olarak kubiti başlangıç durumuna getireceğiz ve ardından `H` işlemini kullanarak süper konuma alacağız.</span><span class="sxs-lookup"><span data-stu-id="8ec52-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="8ec52-226">Ardından, ilk qubit 'i ölçüyoruz, `CNOT` *denetlenen-Not*için temsil eden yeni bir işlem () kullanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="8ec52-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for *Controlled-NOT*.</span></span>  <span data-ttu-id="8ec52-227">Bu işlemi iki qubit üzerinde çalıştırmanın sonucu, birinci qubit ise ikinci qubit 'i çevirmenize neden olur `One` .</span><span class="sxs-lookup"><span data-stu-id="8ec52-227">The result of running this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="8ec52-228">Şimdi iki kubit de dolaşık hale geldi.</span><span class="sxs-lookup"><span data-stu-id="8ec52-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="8ec52-229">İlk kubit için istatistiklerimiz değişmemiştir (ölçüm sonrasında `Zero` veya `One` olma olasılığı %50’dir) ama şimdi ikinci kubiti ölçtüğümüzde ilk kubitte ölçülenle __her zaman__ aynı olduğu görülür.</span><span class="sxs-lookup"><span data-stu-id="8ec52-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="8ec52-230">`CNOT` geçidimiz iki kubiti dolaşık hale getirmiş, bu şekilde ilkine olanın aynısı diğerine de olmuştur.</span><span class="sxs-lookup"><span data-stu-id="8ec52-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="8ec52-231">Ölçümleri ters çevirirseniz (ilk kubitten önce ikincisini yaparsanız), aynı durum ortaya çıkar.</span><span class="sxs-lookup"><span data-stu-id="8ec52-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="8ec52-232">İlk ölçüm rastgele olacak ve ikincisi ilkinde bulunanla aynı yolu izleyecektir.</span><span class="sxs-lookup"><span data-stu-id="8ec52-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="8ec52-233">Yapacağımız ilk şey, bir yerine iki qubit ayırır `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="8ec52-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="8ec52-234">Bu sayede `TestBellState` işleminde ölçüm yapmadan (`M`) önce yeni bir işlem (`CNOT`) ekleyebileceğiz:</span><span class="sxs-lookup"><span data-stu-id="8ec52-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="8ec52-235">İlk kubiti başlatarak, başladığımızda kubitin her zaman `Zero` durumunda olduğundan emin olmak için bir `SetQubitState` işlemi daha eklemiştik.</span><span class="sxs-lookup"><span data-stu-id="8ec52-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="8ec52-236">Serbest bırakmadan önce ikinci kubiti de sıfırlamamız gerekiyor.</span><span class="sxs-lookup"><span data-stu-id="8ec52-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="8ec52-237">Yordamın tamamı şimdi şöyle görünür:</span><span class="sxs-lookup"><span data-stu-id="8ec52-237">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="8ec52-238">Bunu çalıştırırsak yine daha önce aldığımız 50-50 sonucunun aynısını alırız.</span><span class="sxs-lookup"><span data-stu-id="8ec52-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="8ec52-239">Öte yandan biz, ölçülen ilk kubite ikinci kubitin nasıl tepki gösterdiğiyle ilgileniyoruz.</span><span class="sxs-lookup"><span data-stu-id="8ec52-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="8ec52-240">Bu istatistiği `TestBellState` işleminin yeni bir sürümüyle ekleriz:</span><span class="sxs-lookup"><span data-stu-id="8ec52-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="8ec52-241">Yeni dönüş değeri (`agree`), ilk kubitten gelen ölçümün ikinci kubitin ölçümüyle her eşleşmesinin kaydını tutar.</span><span class="sxs-lookup"><span data-stu-id="8ec52-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="8ec52-242">Elde ettiğimiz kodu çalıştırma:</span><span class="sxs-lookup"><span data-stu-id="8ec52-242">Running the code we obtain:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

<span data-ttu-id="8ec52-243">Genel bakışta belirtildiği üzere ilk kubit için istatistiklerimiz değişmemiştir (0 veya 1 olma olasılığı %50’dir) ama şimdi ikinci kubiti ölçtüğümüzde ilk kubitte ölçülenle __her zaman__ aynı olduğu görülür. Bunun nedeni bu kubitlerin dolaşık olmasıdır!</span><span class="sxs-lookup"><span data-stu-id="8ec52-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ec52-244">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="8ec52-244">Next steps</span></span>

<span data-ttu-id="8ec52-245">Öğretici [Grover](xref:microsoft.quantum.quickstarts.search) araması, en popüler hisse alım algoritmalarından biri olan Grover araması oluşturma ve çalıştırma hakkında bilgi sağlar ve Q# Bu programın, hisse bilgi işlem ile gerçek sorunları çözümlemek için kullanılabilecek iyi bir örnek sunmaktadır.</span><span class="sxs-lookup"><span data-stu-id="8ec52-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="8ec52-246">[Hisse geliştirme kiti Ile çalışmaya başlamak,](xref:microsoft.quantum.welcome) daha fazla bilgi edinmek ve bu programlama için daha fazla yol önerir Q# .</span><span class="sxs-lookup"><span data-stu-id="8ec52-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
