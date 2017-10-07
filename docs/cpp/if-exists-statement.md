---
title: "__if_exists 문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __if_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3d0eaa00abb1f833ef491fc27bfee01790776edb
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="ifexists-statement"></a>__if_exists 문
`__if_exists` 문은 지정된 식별자가 있는지 여부를 테스트합니다. 식별자가 있는 경우 지정된 문 블록이 실행됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`identifier`|존재 여부를 테스트할 식별자입니다.|  
|`statements`|경우에 실행할 하나 이상의 문을 `identifier` 존재 합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!CAUTION]
>  가장 안정적인 결과를 얻으려면 다음 제약 조건에서 `__if_exists` 문을 사용합니다.  
  
-   템플릿이 아니라 단순 형식에만 `__if_exists` 문을 적용합니다.  
  
-   클래스 내부 또는 외부 모두에서 `__if_exists` 문을 식별자에 적용합니다. 지역 변수에 `__if_exists` 문을 적용하지 마십시오.  
  
-   `__if_exists` 문은 함수의 본문에서만 사용합니다. 함수 본문 외부에서 `__if_exists` 문은 완전히 정의된 형식만 테스트할 수 있습니다.  
  
-   오버로드된 함수에 대해 테스트할 때 특정 양식의 오버로드를 테스트할 수 없습니다.  
  
 보완 하는 `__if_exists` 문이 [__if_not_exists](../cpp/if-not-exists-statement.md) 문.  
  
## <a name="example"></a>예제  
 다음 예제에서는 템플릿을 사용하지만, 이는 권장되는 방법은 아닙니다.  
  
```  
// the__if_exists_statement.cpp  
// compile with: /EHsc  
#include <iostream>  
  
template<typename T>  
class X : public T {  
public:  
   void Dump() {  
      std::cout << "In X<T>::Dump()" << std::endl;  
  
      __if_exists(T::Dump) {  
         T::Dump();  
      }  
  
      __if_not_exists(T::Dump) {  
         std::cout << "T::Dump does not exist" << std::endl;  
      }  
   }     
};  
  
class A {  
public:  
   void Dump() {  
      std::cout << "In A::Dump()" << std::endl;  
   }  
};  
  
class B {};  
  
bool g_bFlag = true;  
  
class C {  
public:  
   void f(int);  
   void f(double);  
};  
  
int main() {   
   X<A> x1;  
   X<B> x2;  
  
   x1.Dump();  
   x2.Dump();  
  
   __if_exists(::g_bFlag) {  
      std::cout << "g_bFlag = " << g_bFlag << std::endl;  
   }  
  
   __if_exists(C::f) {  
      std::cout << "C::f exists" << std::endl;  
   }  
  
   return 0;  
}  
```  
  
## <a name="output"></a>출력  
  
```  
In X<T>::Dump()  
In A::Dump()  
In X<T>::Dump()  
T::Dump does not exist  
g_bFlag = 1  
C::f exists  
```  
  
## <a name="see-also"></a>참고 항목  
 [선택 문](../cpp/selection-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [__if_not_exists 문](../cpp/if-not-exists-statement.md)
