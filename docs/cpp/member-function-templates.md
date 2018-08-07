---
title: 멤버 함수 템플릿 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function templates, member functions
ms.assetid: 83d51835-6a27-40ed-997c-7d90dc9182d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7767b833fb80926e425e14a209c3d97a778e72b5
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404228"
---
# <a name="member-function-templates"></a>멤버 함수 템플릿

멤버 템플릿이라는 용어는 멤버 함수 템플릿과 중첩된 클래스 템플릿을 둘 다 나타냅니다. 멤버 함수 템플릿은 클래스나 클래스 템플릿의 멤버인 템플릿 함수입니다.  
  
 멤버 함수는 여러 컨텍스트에서 함수 템플릿이 될 수 있습니다. 클래스 템플릿의 모든 함수는 제네릭이지만 멤버 템플릿 또는 멤버 함수 템플릿이라고는 하지 않습니다. 이 멤버 함수가 고유한 템플릿 인수를 가질 경우 멤버 함수 템플릿으로 간주됩니다.  
  
## <a name="example"></a>예

 비템플릿 또는 템플릿 클래스의 멤버 함수 템플릿은 템플릿 매개 변수를 사용하여 함수 템플릿으로 선언됩니다.  
  
```cpp
// member_function_templates.cpp  
struct X  
{  
   template <class T> void mf(T* t) {}  
};  
  
int main()  
{  
   int i;  
   X* x = new X();  
   x->mf(&i);  
}  
```  
  
## <a name="example"></a>예

 다음 예제에서는 템플릿 클래스의 멤버 함수 템플릿을 보여 줍니다.  
  
```cpp
// member_function_templates2.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u)  
   {  
   }  
};  
  
int main()  
{  
}  
```  
  
## <a name="example"></a>예
  
```cpp
// defining_member_templates_outside_class.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u);  
};  
  
template<typename T> template <typename U>  
void X<T>::mf(const U &u)  
{  
}  
  
int main()  
{  
}  
```  
  
## <a name="example"></a>예

 지역 클래스에는 멤버 템플릿이 허용되지 않습니다.  
  
 멤버 템플릿 함수는 가상 함수가 될 수 없으며 기본 클래스 가상 함수와 같은 이름으로 선언된 경우 기본 클래스의 가상 함수를 재정의할 수 없습니다.  
  
다음 예제에서는 템플릿 기반 사용자 정의 변환을 보여 줍니다.  
  
```cpp
// templated_user_defined_conversions.cpp  
template <class T>  
struct S  
{  
   template <class U> operator S<U>()  
   {  
      return S<U>();  
   }  
};  
  
int main()  
{  
   S<int> s1;  
   S<long> s2 = s1;  // Convert s1 using UDC and copy constructs S<long>.  
}  
```  
  
## <a name="see-also"></a>참고자료
 [함수 템플릿](../cpp/function-templates.md)