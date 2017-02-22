---
title: "Checked Iterators | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SECURE_SCL"
  - "_SECURE_SCL_THROWS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "확인된 반복기"
  - "반복기, checked"
  - "안전한 라이브러리"
  - "안전한 라이브러리, 표준 C++ 라이브러리"
  - "안전한 표준 C++ 라이브러리"
ms.assetid: cfc87df8-e3d9-403b-ab78-e9483247d940
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# Checked Iterators
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

확인된 반복기는 컨테이너 경계를 덮어쓰지 않습니다.  
  
 확인된 반복기는 릴리스 빌드 및 디버그 빌드에 적용됩니다.  디버그 모드에서 컴파일할 때 반복기를 사용하는 방법은 [Debug Iterator Support](../standard-library/debug-iterator-support.md)을 참조하십시오.  
  
## 설명  
 확인된 반복기로 생성된 경고를 표시하지 않는 방법은 [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md)를 참조하십시오.  
  
 확인된 반복기 기능에서 다음과 같은 기호를 사용할 수 있습니다.  
  
 `_SECURE_SCL`  
 `_SECURE_SCL`을 1로 정의한 경우 반복기를 안전하지 않게 사용하면 런타임 오류가 발생하고 프로그램이 종료됩니다.  0으로 정의한 경우 확인된 반복기를 사용하지 않도록 설정됩니다.  기본적으로 `_SECURE_SCL` 값은 릴리스 빌드에 대해 0이며 디버그 빌드에 대해 1입니다.  
  
> [!IMPORTANT]
>  `_ITERATOR_DEBUG_LEVEL`을 사용하여 [\_SECURE\_SCL](../standard-library/secure-scl.md)을 제어합니다.  자세한 내용은 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)을 참조하십시오.  
  
 `_SECURE_SCL`을 1로 정의한 경우 다음 SCL 확인을 수행합니다.  
  
-   모든 표준 반복기\(예: [vector::iterator](../Topic/vector::iterator.md)\)를 확인합니다.  
  
-   출력 반복기가 확인된 반복기인 경우 표준 함수\(예: [std::copy](../Topic/copy.md)\)에 대한 호출에서 확인된 동작을 얻을 수 있습니다.  
  
-   출력 반복기가 확인되지 않은 반복기일 경우 표준 함수에 대한 호출에서 컴파일러 경고가 발생합니다.  
  
-   다음 함수에서는 컨테이너 경계를 넘어 액세스할 경우 런타임 오류가 발생합니다.  
  
|||||  
|-|-|-|-|  
|[basic\_string::operator](../Topic/basic_string::operator.md)|[bitset::operator](../Topic/bitset::operator.md)|[deque::back](../Topic/deque::back.md)|[deque::front](../Topic/deque::front.md)|  
|[deque::operator](../Topic/deque::operator.md)|[list::back](../Topic/list::back.md)|[list::front](../Topic/list::front.md)|[queue::back](../Topic/queue::back.md)|  
|[queue::front](../Topic/queue::front.md)|[vector::operator](../Topic/vector::operator.md)|[vector::back](../Topic/vector::back.md)|[vector::front](../Topic/vector::front.md)|  
  
 `_SECURE_SCL`을 0으로 정의한 경우  
  
-   모든 표준 반복기가 확인되지 않습니다\(반복기가 컨테이너 경계 밖으로 이동할 수 있으며 정의되지 않은 동작이 됩니다\).  
  
-   출력 반복기가 확인된 반복기인 경우 표준 함수\(예: `std::copy`\)에 대한 호출에서 확인된 동작을 얻을 수 있습니다.  
  
-   출력 반복기가 확인되지 않은 반복기인 경우 표준 함수\(예: `std::copy`\)에 대한 호출에서 확인되지 않은 동작을 얻을 수 있습니다.  
  
 확인된 반복기는 컨테이너 경계를 넘어 이동하려고 할 때 `invalid_parameter_handler`를 호출하는 반복기를 가리킵니다.  `invalid_parameter_handler`에 대한 자세한 내용은 [매개 변수 유효성 검사](../c-runtime-library/parameter-validation.md)을 참조하십시오.  
  
 [checked\_array\_iterator 클래스](../standard-library/checked-array-iterator-class.md) 및 [unchecked\_array\_iterator 클래스](../standard-library/unchecked-array-iterator-class.md)는 확인된 반복기를 지원하는 반복기 어댑터입니다.  
  
## 예제  
 `_SECURE_SCL 1`를 사용하여 컴파일할 경우 특정 클래스의 인덱싱 연산자를 사용하여 컨테이너 경계 밖에 있는 요소에 액세스하려고 하면 런타임 오류가 발생합니다.  
  
```cpp  
// checked_iterators_1.cpp  
// cl.exe /Zi /MDd /EHsc /W4  
  
#define _ITERATOR_DEBUG_LEVEL 1  
// implies #define _SECURE_SCL 1  
  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
int main()   
{  
    vector<int> v;  
    v.push_back(67);  
  
    int i = v[0];  
    cout << i << endl;  
  
    i = v[1]; // triggers invalid parameter handler  
};  
  
```  
  
 이 프로그램은 "67"을 출력한 다음 실패에 대한 자세한 정보가 들어 있는 어설션 실패 대화 상자를 팝업으로 표시합니다.  
  
## 예제  
 마찬가지로, `_SECURE_SCL 1`을 사용하여 컴파일할 경우 컨테이너가 비어 있을 때 특정 클래스의 전면 또는 후면을 사용하여 요소에 액세스하려고 하면 런타임 오류가 발생합니다.  
  
```cpp  
// checked_iterators_2.cpp  
// cl.exe /Zi /MDd /EHsc /W4  
  
#define _ITERATOR_DEBUG_LEVEL 1  
// implies #define _SECURE_SCL 1  
  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
int main()   
{  
    vector<int> v;  
  
    int& i = v.front(); // triggers invalid parameter handler  
};  
  
```  
  
 이 프로그램은 실패에 대한 자세한 정보가 들어 있는 어설션 실패 대화 상자를 팝업으로 표시합니다.  
  
 다음 코드에는 다양한 반복기 사용 사례 시나리오에 대한 설명과 각각에 대한 주석이 나와 있습니다.  
  
```cpp  
// cl.exe /MTd /EHsc /W4  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <iterator>  
#include <numeric>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v(16);  
    iota(v.begin(), v.end(), 0);  
    print("v: ", v);  
  
    // OK: vector::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (an overrun will trigger a debug assertion)  
    // NOTE: This applies only when raw arrays are given to STL algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (an overrun will trigger undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (an overrun will trigger a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode  
    // (it performs no checking, so an overrun will trigger undefined behavior)  
    int a8[16];  
    int * p8 = a8;  
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
  
```  
  
## Output  
 이전 섹션의 코드를 `cl.exe /EHsc /W4 /MTd`로 컴파일하면 다음과 같은 컴파일러 오류가 발생하지만 실행 파일에서는 오류 없이 컴파일됩니다.  
  
```  
algorithm(1026) : warning C4996: 'std::_Transform1': Function call with parameters that may be unsafe - this call rel  
ies on the caller to check that the passed values are correct. To disable this warning, use -D_SCL_SECURE_NO_WARNINGS. See documentation on how to use Visual C++ 'Checked Iterators'  
```  
  
 다음 출력에서 콘솔 응용 프로그램 실행 파일 실행 결과:  
  
```  
v: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15  
v2: 0 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30  
v3: 0 3 6 9 12 15 18 21 24 27 30 33 36 39 42 45  
a4: 0 4 8 12 16 20 24 28 32 36 40 44 48 52 56 60  
a5: 0 5 10 15 20 25 30 35 40 45 50 55 60 65 70 75  
a6: 0 6 12 18 24 30 36 42 48 54 60 66 72 78 84 90  
a7: 0 7 14 21 28 35 42 49 56 63 70 77 84 91 98 105  
a8: 0 8 16 24 32 40 48 56 64 72 80 88 96 104 112 120  
```  
  
## 참고 항목  
 [STL 개요](../standard-library/cpp-standard-library-overview.md)   
 [Debug Iterator Support](../standard-library/debug-iterator-support.md)