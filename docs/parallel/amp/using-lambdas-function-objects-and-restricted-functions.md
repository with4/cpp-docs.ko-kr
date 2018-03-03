---
title: "람다, 함수 개체 및 제한 된 함수를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: afec84ba6e3c007e576c37b4a7afc71fe62691ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-lambdas-function-objects-and-restricted-functions"></a>람다, 함수 개체 및 제한 함수 사용
액셀러레이터에서 실행 하려는 하는 c + + AMP 코드에 대 한 호출에서 인수로 지정 된 [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) 메서드. 람다 식 또는 함수 개체 (함수)를 해당 인수로 제공할 수 있습니다. 또한 람다 식 또는 함수 개체는 c + + AMP 제한 함수를 호출할 수 있습니다. 이 항목 람다, 함수 개체 및 제한 된 기능을 보여 주기 위해 배열 추가 알고리즘을 사용 합니다. 다음 예제에서는 c + + AMP 코드 없이 알고리즘을 보여 줍니다. 동일한 길이의 두 1 차원 배열이 생성 됩니다. 해당 정수 요소는 추가 하 고 세 번째 1 차원 배열에 저장 됩니다. C + + AMP 사용 되지 않습니다.  
  
```cpp  
void CpuMethod() {  
 
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
 
    for (int idx = 0; idx <5; idx++)  
 {  
    sumCPP[idx] = aCPP[idx] + bCPP[idx];  
 }  
 
    for (int idx = 0; idx <5; idx++)  
 {  
    std::cout <<sumCPP[idx] <<"\n";  
 }  
}  
 
```  
  
## <a name="lambda-expression"></a>람다 식  
 람다 식을 사용 하 여 c + + AMP를 사용 하 여 코드를 다시 작성 하는 가장 간단한 방법은 됩니다.  
  
```cpp  
void AddArraysWithLambda() {  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
 
    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

 
    parallel_for_each(
 sum.extent, 
 [=](index<1> idx) restrict(amp)  
 {  
    sum[idx] = a[idx] + b[idx];  
 });

 
    for (int i = 0; i <5; i++) {  
    std::cout <<sum[i] <<"\n";  
 }  
}  
 
```  
  
 람다 식은 하나의 인덱싱 매개 변수를 포함 해야를 포함 해야 `restrict(amp)`합니다. 예제에서는 [array_view](../../parallel/amp/reference/array-view-class.md) `sum` 개체에는 순위 1입니다. 따라서이 람다 문에 매개 변수는 [인덱스](../../parallel/amp/reference/index-class.md) 1 순위를 가진 개체를 합니다. 런타임 시, 람다 식을 한 번 실행 됩니다 각 요소에 대해는 [array_view](../../parallel/amp/reference/array-view-class.md) 개체입니다. 자세한 내용은 참조 [람다 식 구문](../../cpp/lambda-expression-syntax.md)합니다.  
  
## <a name="function-object"></a>Function 개체  
 개체를 함수 가속기 코드를 팩터링 할 수 있습니다.  
  
```cpp  
class AdditionFunctionObject  
{  
public:  
    AdditionFunctionObject(const array_view<int, 1>& a,  
    const array_view<int, 1>& b,  
    const array_view<int, 1>& sum)  
 : a(a), b(b), sum(sum)  
 {  
 }  
 
    void operator()(index<1> idx) restrict(amp)  
 {  
    sum[idx] = a[idx] + b[idx];  
 }  
 
private:  
    array_view<int, 1> a;  
    array_view<int, 1> b;  
    array_view<int, 1> sum;  
};  
 
void AddArraysWithFunctionObject() {  
 
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
 
    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

 
    parallel_for_each(
 sum.extent, 
    AdditionFunctionObject(a, b, sum));

 
    for (int i = 0; i <5; i++) {  
    std::cout <<sum[i] <<"\n";  
 }  
}  
 
```  

 함수 개체는 생성자를 포함 해야 하 고 함수 호출 연산자 오버 로드를 포함 해야 합니다. 함수 호출 연산자는 하나의 인덱싱 매개 변수를 포함 해야 합니다. 함수 개체의 인스턴스를 두 번째 인수로 전달 되는 [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) 메서드. 이 예제에서는 세 가지 [array_view](../../parallel/amp/reference/array-view-class.md) 개체를 함수 개체 생성자에 전달 합니다. [array_view](../../parallel/amp/reference/array-view-class.md) 개체 `sum` 1의 순위가 합니다. 따라서 함수 호출 연산자에 매개 변수는 한 [인덱스](../../parallel/amp/reference/index-class.md) 1 순위를 가진 개체를 합니다. 런타임 시 함수는 실행 한 번의 각 요소에 대 한는 [array_view](../../parallel/amp/reference/array-view-class.md) 개체입니다. 자세한 내용은 참조 [함수 호출](../../cpp/function-call-cpp.md) 및 [c + + 표준 라이브러리에 함수 개체](../../standard-library/function-objects-in-the-stl.md)합니다.  
  
## <a name="c-amp-restricted-function"></a>C + + AMP 제한 함수  
 추가 제한 된 함수를 만들고 람다 식 또는 함수 개체에서 호출 하 여 액셀러레이터 키 코드를 팩터링 할 수 있습니다. 다음 코드 예제에서는 람다 식에서 제한 된 함수를 호출 하는 방법을 보여 줍니다.  
  
```cpp  
void AddElementsWithRestrictedFunction(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)  
{  
    sum[idx] = a[idx] + b[idx];  
}  
 
void AddArraysWithFunction() {  
 
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
 
    array_view<int, 1> a(5, aCPP);

    array_view<int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

 
    parallel_for_each(
 sum.extent, 
 [=](index<1> idx) restrict(amp)  
 {  
    AddElementsWithRestrictedFunction(idx, sum, a, b);

 });

 
    for (int i = 0; i <5; i++) {  
    std::cout <<sum[i] <<"\n";  
 }  
}  
 
```  
  
 제한 된 함수를 포함 해야 `restrict(amp)` 에 설명 된 제한 사항을 준수 하 고 [제한 (c + + AMP)](../../cpp/restrict-cpp-amp.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + AMP (c + + Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [람다 식 구문](../../cpp/lambda-expression-syntax.md)   
 [함수 호출](../../cpp/function-call-cpp.md)   
 [C + + 표준 라이브러리에 함수 개체](../../standard-library/function-objects-in-the-stl.md)   
 [restrict(C++ AMP)](../../cpp/restrict-cpp-amp.md)

