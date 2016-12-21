---
title: "람다, 함수 개체 및 제한 함수 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
caps.latest.revision: 10
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 람다, 함수 개체 및 제한 함수 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

액셀러레이터에서 실행하려는 C\+\+ AMP 코드는 [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) 메서드로의 호출에서 인수로 지정됩니다.  해당 인수로 람다 식 또는 함수 개체\(functor\)를 제공할 수 있습니다.  또한 람다 식 또는 함수 개체는 C\+\+ 제한 함수를 호출할 수 있습니다.  이 항목은 람다 식, 함수 개체 및 제한된 기능을 보여 주기 위해 배열 추가 알고리즘을 사용합니다.  다음 예제는 C\+\+ AMP 코드가 없는 알고리즘을 보여 줍니다.  같은 길이의 1차원 배열 두 개가 만들어집니다.  해당 정수 요소를 추가하고 세 번째 1차원 배열에 저장합니다.  C\+\+ AMP는 사용되지 않습니다.  
  
```cpp  
  
void CpuMethod() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        sumCPP[idx] = aCPP[idx] + bCPP[idx];  
    }  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        std::cout << sumCPP[idx] << "\n";  
    }  
}  
  
```  
  
## 람다 식  
 람다 식을 사용하는 것은 C\+\+ AMP를 사용하여 코드를 다시 작성하는 가장 직접적인 방법입니다.  
  
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
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 람다 식은 하나의 인덱싱 매개 변수를 포함해야 하며 `restrict(amp)`를 포함해야 합니다．  이 예에서, [array\_view](../../parallel/amp/reference/array-view-class.md) `sum` 개체는 1 순위를 갖습니다.  따라서 람다 식에 대한 변수는 차수가 1인 [인덱스](../../parallel/amp/reference/index-class.md) 개체입니다.  런타임 시 [array\_view](../../parallel/amp/reference/array-view-class.md) 개체의 각 요소에 대해 람다 식이 한 번씩 실행됩니다.  자세한 내용은 [람다 식 구문](../../cpp/lambda-expression-syntax.md)을 참조하십시오.  
  
## Function 개체  
 액셀러레이터 코드를 함수 개체로 분할할 수 있습니다.  
  
```cpp  
  
class AdditionFunctionObject  
{  
public:  
    AdditionFunctionObject(const array_view<int, 1>& a,  
        const array_view<int, 1>& b,  
        const array_view<int, 1>& sum  
    )  
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
        AdditionFunctionObject(a, b, sum)  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 함수 개체는 생성자를 포함해야 하고 함수 호출 연산자의 오버로드를 포함해야 합니다.  함수 호출 연산자는 하나의 인덱싱 매개 변수를 포함해야 합니다.  함수 개체의 인스턴스가 [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) 메서드의 두 번째 인수로 전달됩니다.  이 예에서는 세 개의 [array\_view](../../parallel/amp/reference/array-view-class.md) 개체가 함수 개체 생성자에 전달됩니다.  [array\_view](../../parallel/amp/reference/array-view-class.md)`sum` 개체는 차수가 1입니다.  따라서 함수 호출 연산자에 대한 변수는 차수가 1인 [인덱스](../../parallel/amp/reference/index-class.md) 개체입니다.  런타임 시 [array\_view](../../parallel/amp/reference/array-view-class.md) 개체의 각 요소에 대해 함수가 한 번씩 실행됩니다.  자세한 내용은 [함수 호출](../../cpp/function-call-cpp.md) 및 [STL의 함수 개체](../../standard-library/function-objects-in-the-stl.md)를 참조하십시오.  
  
## C\+\+ AMP 제한 함수  
 제한적 함수를 만들고 람다 식 또는 함수 개체에서 호출하여 액셀러레이터 코드를 추가로 채울 수 있습니다.  다음 코드 예제는 람다 식에서 제한 함수를 호출하는 방법을 보여 줍니다.  
  
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
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 제한된 함수에는 `restrict(amp)`가 포함되어야 하며 [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)에 설명된 제한을 따라야 합니다.  
  
## 참고 항목  
 [C\+\+ AMP\(C\+\+ Accelerated Massive Parallelism\)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [람다 식 구문](../../cpp/lambda-expression-syntax.md)   
 [함수 호출](../../cpp/function-call-cpp.md)   
 [STL의 함수 개체](../../standard-library/function-objects-in-the-stl.md)   
 [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)