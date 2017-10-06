---
title: "람다 식 구문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++], syntax
ms.assetid: 5d6154a4-f34d-4a15-970d-7e7de45f54e9
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9daa1ce8d7b55f71113dcf7559394715bd93c604
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="lambda-expression-syntax"></a>람다 식 구문
이 문서에서는 람다 식의 구문과 구성 요소에 대해 설명합니다. 람다 식에 대 한 참조 [람다 식](../cpp/lambda-expressions-in-cpp.md)합니다.  
  
## <a name="function-objects-vs-lambdas"></a>함수 개체와 람다  
 코드를 작성할 때는 아마도 함수 포인터와 함수 개체를 통해 문제를 해결 하 고 사용 하는 경우에 특히 계산을 수행 하 [c + + 표준 라이브러리 알고리즘](../cpp/algorithms-modern-cpp.md)합니다. 함수 포인터와 함수 개체는 각각 장단점이 있습니다. 예를 들어 함수 포인터는 최소한의 구문 오버헤드가 있지만 범위 내에 상태를 유지하지 않으며 함수 개체는 상태를 유지할 수 있지만 클래스 정의의 구문 오버헤드가 필요합니다.  
  
 람다는 함수 포인터와 함수 개체의 이점을 결합하여 단점을 방지합니다. 람다는 함수 개체와 마찬가지로 유연하고 상태를 유지할 수 있지만 함수 개체와 다르게 간단한 구문은 명시적인 클래스 정의가 필요하지 않습니다. 람다를 사용하면 코드를 더 쉽게 작성할 수 있고 해당 함수 개체에 대한 코드보다 오류 발생 가능성이 적습니다.  
  
 다음 예제에서는 람다 사용과 함수 개체 사용을 비교합니다. 첫 번째 예제에서는 람다를 사용하여 `vector` 개체의 각 요소가 짝수이든 홀수이든 콘솔에 인쇄합니다. 두 번째 예제에서는 함수 개체를 사용하여 같은 작업을 수행합니다.  
  
## <a name="example-1-using-a-lambda"></a>예제 1: 람다 사용하기  
 이 예제에서는 `for_each` 함수에 람다를 전달합니다. 람다는 `vector` 개체의 각 요소가 짝수인지 홀수인지 보여 주는 결과를 인쇄합니다.  
  
### <a name="code"></a>코드  
  
```cpp  
// even_lambda.cpp  
// compile with: cl /EHsc /nologo /W4 /MTd  
#include <algorithm>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main()   
{  
   // Create a vector object that contains 10 elements.  
   vector<int> v;  
   for (int i = 1; i < 10; ++i) {  
      v.push_back(i);  
   }  
  
   // Count the number of even numbers in the vector by   
   // using the for_each function and a lambda.  
   int evenCount = 0;  
   for_each(v.begin(), v.end(), [&evenCount] (int n) {  
      cout << n;  
      if (n % 2 == 0) {  
         cout << " is even " << endl;  
         ++evenCount;  
      } else {  
         cout << " is odd " << endl;  
      }  
   });  
  
   // Print the count of even numbers to the console.  
   cout << "There are " << evenCount   
        << " even numbers in the vector." << endl;  
}  
```  
  
### <a name="output"></a>출력  
  
```Output  
1 is odd  
2 is even  
3 is odd  
4 is even  
5 is odd  
6 is even  
7 is odd  
8 is even  
9 is odd  
There are 4 even numbers in the vector.  
  
```  
  
### <a name="comments"></a>설명  
 이 예제에서 `for_each` 함수에 대한 세 번째 인수는 람다입니다. `[&evenCount]` 부분은 식의 캡처 절을 지정하고`(int n)`은 매개 변수 목록을 지정하고 나머지 부분은 식의 본문을 지정합니다.  
  
## <a name="example-2-using-a-function-object"></a>예제 2: 함수 개체 사용하기  
 때로는 람다가 너무 비대해져서 이전 예제보다 훨씬 더 확장할 수 없습니다. 다음 예제에서는 람다 대신에 함수 개체를 `for_each` 함수와 함께 사용하여 예제 1과 같은 결과를 생성합니다. 두 예제 모두 `vector` 개체에 짝수의 수를 저장합니다. 연산의 상태를 유지하기 위해 `FunctorClass` 클래스는 `m_evenCount` 변수를 멤버 변수로 참조하면서 저장합니다. 연산을 수행하려면, `FunctorClass`는 함수 호출 연산자, `operator()`를 구현합니다. Visual C++ 컴파일러는 성능과 사이즈가 예제 1의 람다 코드와 비슷한 코드를 생성합니다. 이 문서의 문제와 같은 기본적인 문제의 경우 함수 개체 디자인보다 간단한 람다 디자인이 더 좋습니다. 그러나 이 기능에 나중에 중요한 확장이 필요할 수 있다면 코드 유지 관리를 더 수월하게 할 수 있도록 함수 개체 디자인을 사용합니다.  
  
 에 대 한 자세한 내용은 `operator()`, 참조 [함수 호출](../cpp/function-call-cpp.md)합니다. 에 대 한 자세한 내용은 `for_each` 함수, 참조 [for_each](../standard-library/algorithm-functions.md#for_each)합니다.  
  
### <a name="code"></a>코드  
  
```cpp  
// even_functor.cpp  
// compile with: /EHsc  
#include <algorithm>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class FunctorClass  
{  
public:  
    // The required constructor for this example.  
    explicit FunctorClass(int& evenCount)  
        : m_evenCount(evenCount) { }  
  
    // The function-call operator prints whether the number is  
    // even or odd. If the number is even, this method updates  
    // the counter.  
    void operator()(int n) const {  
        cout << n;  
  
        if (n % 2 == 0) {  
            cout << " is even " << endl;  
            ++m_evenCount;  
        } else {  
            cout << " is odd " << endl;  
        }  
    }  
  
private:  
    // Default assignment operator to silence warning C4512.  
    FunctorClass& operator=(const FunctorClass&);  
  
    int& m_evenCount; // the number of even variables in the vector.  
};  
  
int main()  
{  
    // Create a vector object that contains 10 elements.  
    vector<int> v;  
    for (int i = 1; i < 10; ++i) {  
        v.push_back(i);  
    }  
  
    // Count the number of even numbers in the vector by   
    // using the for_each function and a function object.  
    int evenCount = 0;  
    for_each(v.begin(), v.end(), FunctorClass(evenCount));  
  
    // Print the count of even numbers to the console.  
    cout << "There are " << evenCount  
        << " even numbers in the vector." << endl;  
}  
  
```  
  
## <a name="output"></a>출력  
  
```Output  
1 is odd  
2 is even  
3 is odd  
4 is even  
5 is odd  
6 is even  
7 is odd  
8 is even  
9 is odd  
There are 4 even numbers in the vector.  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../cpp/lambda-expressions-in-cpp.md)   
 [람다 식의 예](../cpp/examples-of-lambda-expressions.md)   
 [생성](../standard-library/algorithm-functions.md#generate)   
 [generate_n](../standard-library/algorithm-functions.md#generate_n)   
 [for_each](../standard-library/algorithm-functions.md#for_each)   
 [예외 사양 (throw)](../cpp/exception-specifications-throw-cpp.md)   
 [컴파일러 경고 (수준 1) C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)   
 [Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md)
