---
title: QDK ile kendi sınıflandırıcınızı tasarlama
description: Hisse devresini merkezli sınıflandırıcı için devre modellerini tasarlamaya yönelik temel kavramları öğrenin.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: 4899336f437c1b7712a7831b97fd6ec1431b59a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909730"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="b4baf-103">Kendi sınıflandırıcınızı tasarlama</span><span class="sxs-lookup"><span data-stu-id="b4baf-103">Design your own classifier</span></span>

<span data-ttu-id="b4baf-104">Bu kılavuzda, hisse kullanım merkezli sınıflandırıcılara yönelik devre modelleri tasarımının arkasındaki temel kavramları öğreneceksiniz.</span><span class="sxs-lookup"><span data-stu-id="b4baf-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="b4baf-105">Klasik derinlemesine öğrenime göre, belirli bir mimari seçmek için genel bir kural yoktur.</span><span class="sxs-lookup"><span data-stu-id="b4baf-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="b4baf-106">Soruna bağlı olarak bazı mimarilerin diğerlerinden daha iyi hale getirecektir.</span><span class="sxs-lookup"><span data-stu-id="b4baf-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="b4baf-107">Ancak, devre tasarımı sırasında yararlı olabilecek bazı kavramlar vardır:</span><span class="sxs-lookup"><span data-stu-id="b4baf-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="b4baf-108">Çok sayıda parametre daha esnek bir model anlamına gelir. Bu, karmaşık sınıflandırma sınırlarını çizmek için uygun olabilecek, ancak büyük/veya çok daha da savunmasız olabilir.</span><span class="sxs-lookup"><span data-stu-id="b4baf-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="b4baf-109">Qugeler arasındaki kapıları, hisse ilişkilerimiz arasındaki bağıntıları yakalamak için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="b4baf-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="b4baf-110">Soru-cevap ile sınıflandırıcı derleme\#</span><span class="sxs-lookup"><span data-stu-id="b4baf-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="b4baf-111">Bir sınıflandırıcı oluşturmak için, devre modelimizde parametrized kontrollü döndürmeler birleştirilecek.</span><span class="sxs-lookup"><span data-stu-id="b4baf-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="b4baf-112">Bunu yapmak için, hisse Machine Learning kitaplığında tanımlanan [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) türünü kullanabiliriz.</span><span class="sxs-lookup"><span data-stu-id="b4baf-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="b4baf-113">Bu tür, tanımlayan dört bağımsız değişkeni kabul eder: hedef qubit dizinini, denetim qubits 'in Dizin dizisini, döndürme eksenini ve modeli tanımlayan parametrelerin dizisindeki ilişkili parametrenin dizinini.</span><span class="sxs-lookup"><span data-stu-id="b4baf-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="b4baf-114">Sınıflandırıcının bir örneğini görelim.</span><span class="sxs-lookup"><span data-stu-id="b4baf-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="b4baf-115">[Yarım Moons örneğinde](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), `Training.qs`dosyada tanımlanan aşağıdaki sınıflandırıcıyı bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b4baf-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

<span data-ttu-id="b4baf-116">Burada tanımladığımız özellikler, bir dizi parametre ile birlikte bir dizi `ControlledRotation` öğesi döndüren ve [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel)bir sapma tanımlayan bir işlevdir.</span><span class="sxs-lookup"><span data-stu-id="b4baf-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="b4baf-117">Bu tür, hisse Machine Learning kitaplığı 'nda temel ve sınıflandırıcının tanımlanandır.</span><span class="sxs-lookup"><span data-stu-id="b4baf-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="b4baf-118">Yukarıdaki işlevde tanımlanan devre, veri kümesinin her bir örneğinin iki özellik içerdiği bir sınıflandırıcının parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="b4baf-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="b4baf-119">Bu nedenle, yalnızca iki qubit gerekir.</span><span class="sxs-lookup"><span data-stu-id="b4baf-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="b4baf-120">Devresinin grafik gösterimi:</span><span class="sxs-lookup"><span data-stu-id="b4baf-120">The graphical representation of the circuit is:</span></span>

 ![Devre modeli örneği](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="b4baf-122">Kapı katmanlarını yazmak için kitaplık işlevlerini kullanma</span><span class="sxs-lookup"><span data-stu-id="b4baf-122">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="b4baf-123">Örnek başına 784 özelliklerine sahip bir veri kümeniz olduğunu varsayalım, örneğin, bir veri kümesi gibi 28 × 28 piksel görüntüler.</span><span class="sxs-lookup"><span data-stu-id="b4baf-123">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="b4baf-124">Bu durumda, devreninin genişliği yeterince büyük hale gelir. böylece her bir kapı, her bir ağ geçidinin olası ancak pratik bir görev haline gelir.</span><span class="sxs-lookup"><span data-stu-id="b4baf-124">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="b4baf-125">Bu nedenle hisse Machine Learning kitaplığı, otomatik olarak parametrized döndürmeler katmanları oluşturmak için bir araç kümesi sağlar.</span><span class="sxs-lookup"><span data-stu-id="b4baf-125">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="b4baf-126">Örnek olarak, işlev [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) , her bir qubit için tek bir dönüşle, her bir parametrized farklı bir model parametresi tarafından bir dönüşle, belirli bir eksen boyunca denetlenmeyen tek qubit döndürmeler dizisini döndürür.</span><span class="sxs-lookup"><span data-stu-id="b4baf-126">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="b4baf-127">Örneğin, `LocalRotationsLayer(4, X)` aşağıdaki kapı kümesini döndürür:</span><span class="sxs-lookup"><span data-stu-id="b4baf-127">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![Yerel döndürmeler katmanı](~/media/local_rotations_layer.PNG)

<span data-ttu-id="b4baf-129">Devre tasarımını kolaylaştırmak için kullanılabilen tüm araçları öğrenmek amacıyla [hisse Machine Learning kitaplığının API referenece](xref:microsoft.quantum.machinelearning) 'yi araştırmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="b4baf-129">We recommend you to explore the [API referenece of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b4baf-130">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="b4baf-130">Next steps</span></span>

 <span data-ttu-id="b4baf-131">Örnekler tarafından sağlanan örneklerde farklı yapılar deneyin.</span><span class="sxs-lookup"><span data-stu-id="b4baf-131">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="b4baf-132">Modelin performansına ilişkin herhangi bir değişiklik mi görüyorsunuz?</span><span class="sxs-lookup"><span data-stu-id="b4baf-132">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="b4baf-133">Sonraki öğreticide [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), sınıflandırıcıın yeni mimarilerini denemek ve araştırmak için veri kümelerinin nasıl yükleneceğini öğreneceksiniz.</span><span class="sxs-lookup"><span data-stu-id="b4baf-133">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>