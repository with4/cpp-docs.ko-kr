---
title: "종속적인 형식에 대 한 이름 확인 | Microsoft Docs"
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
ms.assetid: 34066bb4-0c79-4fd8-bda7-539a60a277ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d8978e38745f088884bbf28ffb0ab98cfb87895
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="name-resolution-for-dependent-types"></a>종속적인 형식에 대한 이름 확인
사용 하 여 **typename** 정규화 된 이름에 지정된 된 정규화 이름이 형식을 식별 함을 컴파일러에 지시 하는 템플릿 정의 대 한 합니다. 자세한 내용은 참조 [typename](../cpp/typename.md)합니다.  
  
```cpp  
// template_name_resolution1.cpp  
#include <stdio.h>  
template <class T> class X  
{  
public:  
   void f(typename T::myType* mt) {}  
};  
  
class Yarg  
{  
public:  
   struct myType { };  
};  
  
int main()  
{  
   X<Yarg> x;  
   x.f(new Yarg::myType());  
   printf("Name resolved by using typename keyword.");  
}  
```  
  
```Output  
Name resolved by using typename keyword.  
```  
  
 종속 이름에 대 한 이름 조회 템플릿 정의의 컨텍스트에서 이름을 조사-다음 예제에서는이 컨텍스트에서 찾게 `myFunction(char)`-및 템플릿 인스턴스화의 컨텍스트에서 합니다. 다음 예제에서는 템플릿이 main에서 인스턴스화된 따라서는 `MyNamespace::myFunction` 인스턴스화 시점에서 볼 수 있고 더 나은 일치 항목으로 선택 됩니다. `MyNamespace::myFunction`의 이름이 바뀐 경우 `myFunction(char)`이 대신 호출됩니다.  
  
 모든 이름은 종속 이름인 것처럼 확인됩니다. 그러나 충돌 발생 가능성이 있을 경우 철저하게 정규화된 이름을 사용하는 것이 좋습니다.  
  
```cpp  
// template_name_resolution2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void myFunction(char)  
{  
   cout << "Char myFunction" << endl;  
}  
  
template <class T> class Class1  
{  
public:  
   Class1(T i)  
   {  
      // If replaced with myFunction(1), myFunction(char)  
      // will be called  
      myFunction(i);  
}  
};  
  
namespace MyNamespace  
{  
   void myFunction(int)  
   {  
      cout << "Int MyNamespace::myFunction" << endl;  
   }  
};  
  
using namespace MyNamespace;  
  
int main()  
{  
   Class1<int>* c1 = new Class1<int>(100);  
}  
```  
  
### <a name="output"></a>출력  
  
```  
Int MyNamespace::myFunction  
```  
  
### <a name="template-disambiguation"></a>템플릿 명확성  
 [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]는 "템플릿" 키워드를 사용하여 명확성에 대한 C++ 98/03/11 표준 규칙을 적용합니다. 다음 예제에서는 Visual c + + 2010는 모두을 표준에 맞는 줄 수락 합니다.  [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]표준에 맞는 줄만 허용합니다.  
  
```cpp  
#include <iostream>  
#include <ostream>  
#include <typeinfo>  
using namespace std;  
  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    #if defined(NONCONFORMANT)  
        typedef typename AY::Rebind<X>::Other AX; // nonconformant  
    #elif defined(CONFORMANT)  
        typedef typename AY::template Rebind<X>::Other AX; // conformant  
    #else  
        #error Define NONCONFORMANT or CONFORMANT.  
    #endif  
};  
  
int main() {  
    cout << typeid(Container<int, Allocator<float>>::AX).name() << endl;  
}  
```  
  
 기본적으로 C++에서는 `AY::Rebind`가 템플릿이 아니며 컴파일러에서 다음 " `<`"을 less-than으로 해석한다고 가정하기 때문에 명확성 규칙 준수가 필요합니다. C++에 `Rebind`가 템플릿이라는 것을 인지시켜 "`<`"을 꺾쇠로 올바르게 구문 분석할 수 있도록 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이름 확인](../cpp/templates-and-name-resolution.md)