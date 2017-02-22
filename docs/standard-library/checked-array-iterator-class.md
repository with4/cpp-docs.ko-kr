---
title: "checked_array_iterator 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/checked_array_iterator"
  - "checked_array_iterator"
  - "std::checked_array_iterator"
  - "std.checked_array_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "checked_array_iterator"
  - "checked_array_iterator 클래스"
  - "checked_array_iterator, 구문"
ms.assetid: 7f07185e-d588-4ae3-9c4f-84ec4aa25a28
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# checked_array_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 `checked_array_iterator` 클래스를 사용하여 확인한 반복기로 배열 또는 포인터를 변환할 수 있습니다  이러한 경고를 전역적으로 해제하는 대신 이 클래스를 원시 포인터 또는 배열에 대한 래퍼로 목적에 따라 사용하여\([make\_checked\_array\_iterator](../Topic/make_checked_array_iterator.md) 함수 사용\) 확인을 제공하고 확인되지 않은 포인터 경고를 관리합니다.  필요에 따라 [unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md) 클래스의 확인되지 않은 버전을 사용할 수 있습니다.  
  
> [!NOTE]
>  이 클래스는 표준 C\+\+ 라이브러리의 Microsoft 확장입니다.  이 함수를 사용하여 구현한 코드는 이 Microsoft 확장을 지원하지 않는 C\+\+ 표준 빌드 환경으로 이식할 수 없습니다.  이 클래스의 사용을 요구하지 않는 코드를 작성하는 방법을 보여 주는 예는 아래의 두 번째 예제를 참조하세요.  
  
## 구문  
  
```  
template <class _Iterator>  
    class checked_array_iterator;  
```  
  
## 설명  
 이 클래스는 [stdext](../standard-library/stdext-namespace.md) 네임스페이스에 정의됩니다.  
  
 확인된 반복기 기능에 대한 자세한 내용 및 예제 코드는 [Checked Iterators](../standard-library/checked-iterators.md)를 참조하세요.  
  
## 예제  
 다음 샘플은 확인된 배열 반복기를 정의 및 사용하는 방법을 보여 줍니다.  
  
 대상이 복사하는 모든 요소를 보관할 수 없는 크기인 경우, 라인을 변경하는 경우가 해당합니다.  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
```  
  
 끝  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 4));  
```  
  
 런타임 오류가 발생합니다.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[]={0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
  
   // constructor example  
   checked_array_iterator<int*> checked_out_iter(b, 5);  
   copy(a, a + 5, checked_out_iter);  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
}  
```  
  
  **\( 0 1 2 3 4 \)**  
**\( 0 1 2 3 4 \)**   
## 예제  
 표준 C\+\+ 라이브러리 알고리즘을 사용하는 경우 `checked_array_iterator` 클래스의 필요성을 회피하려면 동적으로 할당된 배열 대신 `vector`를 사용해 보세요.  다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main()  
{  
    std::vector<int> v(10);  
    int *arr = new int[10];  
    for (int i = 0; i < 10; ++i)  
    {  
        v[i] = i;  
        arr[i] = i;  
    }  
  
    // std::copy(v.begin(), v.end(), arr); will result in  
    // warning C4996. To avoid this warning while using int *,  
    // use the Microsoft extension checked_array_iterator.  
    std::copy(v.begin(), v.end(),  
              stdext::checked_array_iterator<int *>(arr, 10));  
  
    // Instead of using stdext::checked_array_iterator and int *,  
    // consider using std::vector to encapsulate the array. This will  
    // result in no warnings, and the code will be portable.  
    std::vector<int> arr2(10);    // Similar to int *arr = new int[10];  
    std::copy(v.begin(), v.end(), arr2.begin());  
  
    for (int j = 0; j < arr2.size(); ++j)  
    {  
        cout << " " << arr2[j];  
    }  
    cout << endl;  
  
    return 0;  
}  
```  
  
  **0 1 2 3 4 5 6 7 8 9**   
### 생성자  
  
|||  
|-|-|  
|[checked\_array\_iterator](../Topic/checked_array_iterator::checked_array_iterator.md)|기본 반복기에서 기본 `checked_array_iterator` 또는 `checked_array_iterator`를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[difference\_type](../Topic/checked_array_iterator::difference_type.md)|동일한 컨테이너 안에서 요소를 참조하는 두 `checked_array_iterator` 사이의 차이를 제공하는 형식입니다.|  
|[포인터](../Topic/checked_array_iterator::pointer.md)|`checked_array_iterator`로 주소를 지정하는 요소에 포인터를 제공하는 형식입니다.|  
|[참조](../Topic/checked_array_iterator::reference.md)|`checked_array_iterator`로 주소를 지정하는 요소에 참조를 제공하는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[기본](../Topic/checked_array_iterator::base.md)|`checked_array_iterator`에서 기본 반복기를 복구합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[연산자\=\=](../Topic/checked_array_iterator::operator==.md)|두 `checked_array_iterator`가 같은지 테스트합니다.|  
|[operator\!\=](../Topic/checked_array_iterator::operator!=.md)|두 `checked_array_iterator`가 다른지 테스트합니다.|  
|[operator \<](../Topic/checked_array_iterator::operator%3C.md)|연산자의 좌변에 있는 `checked_array_iterator`가 우변에 있는 `checked_array_iterator`보다 작은지 테스트합니다.|  
|[operator \>](../Topic/checked_array_iterator::operator%3E.md)|연산자의 좌변에 있는 `checked_array_iterator`가 우변에 있는 `checked_array_iterator`보다 큰지 테스트합니다.|  
|[operator \<\=](../Topic/checked_array_iterator::operator%3C=.md)|연산자의 좌변에 있는 `checked_array_iterator`가 우변에 있는 `checked_array_iterator`보다 작거나 같은지 테스트합니다.|  
|[operator \>\=](../Topic/checked_array_iterator::operator%3E=.md)|연산자의 좌변에 있는 `checked_array_iterator`가 우변에 있는 `checked_array_iterator`보다 크거나 같은지 테스트합니다.|  
|[operator\*](../Topic/checked_array_iterator::operator*.md)|`checked_array_iterator`가 주소 지정하는 요소를 반환합니다.|  
|[연산자\-\>](../Topic/checked_array_iterator::operator-%3E.md)|`checked_array_iterator`가 주소 지정하는 요소로 포인터를 반환합니다.|  
|[operator\+\+](../Topic/checked_array_iterator::operator++.md)|`checked_array_iterator`를 다음 요소로 증가시킵니다.|  
|[연산자\-\-](../Topic/checked_array_iterator::operator--.md)|`checked_array_iterator`를 이전 요소로 감소시킵니다.|  
|[operator \+\=](../Topic/checked_array_iterator::operator+=.md)|`checked_array_iterator`에 지정된 오프셋을 추가합니다.|  
|[operator \+](../Topic/checked_array_iterator::operator+.md)|반복기에 오프셋을 추가하고 새 오프셋 위치에서 삽입된 요소를 주소 지정하는 새 `checked_array_iterator`를 반환합니다.|  
|[연산자\-\=](../Topic/checked_array_iterator::operator-=.md)|`checked_array_iterator`에서 지정된 오프셋을 감소시킵니다.|  
|[연산자\-](../Topic/checked_array_iterator::operator-.md)|반복기에서 오프셋을 감소시키고 새로운 오프셋 위치에서 삽입된 요소를 주소 지정하는 새로운 `checked_array_iterator`를 반환합니다.|  
|[operator&#91;&#93;](../Topic/checked_array_iterator::operator.md)|`checked_array_iterator`에서 주소 지정하는 요소의 요소 오프셋으로 지정된 위치 수만큼 참조를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<iterator\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<iterator\>](../standard-library/iterator.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)