---
title: "컴파일러 오류 C2248 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2248
dev_langs:
- C++
helpviewer_keywords:
- C2248
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
caps.latest.revision: 22
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 24977f831d326dab4882a21c70d8dce6da8b1ae9
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-error-c2248"></a>컴파일러 오류 C2248
'*멤버*': 액세스할 수 없습니다 '*access_level*'클래스에 선언 된 멤버'*클래스*'  
  
파생된 클래스의 멤버에 액세스할 수 없습니다 `private` 기본 클래스의 멤버입니다. 액세스할 수 없는 `private` 또는 `protected` 클래스 인스턴스의 멤버입니다.  
  
## <a name="example"></a>예제  
  
다음 샘플에서는 개인 때 C2248 또는 클래스의 보호 된 멤버는 클래스 외부에서 액세스 됩니다. 이 문제를 해결 하려면 이러한 멤버는 클래스 외부에 직접 액세스 하지 않습니다. 공용 멤버 데이터와 멤버 함수를 사용 하 여 클래스와 상호 작용할 수 있습니다.  
  
```cpp  
// C2248_access.cpp 
// compile with: cl /EHsc /W4 C2248_access.cpp 
#include <stdio.h>  

class X {  
public:  
    int  m_publicMember;  
    void setPrivateMember( int i ) {  
        m_privateMember = i;  
        printf_s("\n%d", m_privateMember);  
    }  
protected:  
    int  m_protectedMember;  
  
private:  
    int  m_privateMember;  
} x;  
  
int main() {  
    x.m_publicMember = 4;  
    printf_s("\n%d", x.m_publicMember);  
    x.m_protectedMember = 2; // C2248 m_protectedMember is protected  
    x.m_privateMember = 3;   // C2248  m_privMemb is private  
    x.setPrivateMember(0);   // OK uses public access function  
}  
```  
  
C2248 노출 하는 또 다른 규칙에 따라 문제에는 템플릿 friend와 특수화의 사용입니다. 이 문제를 해결 하려면 선언 friend 템플릿 함수는 빈 매개 변수 목록 template<> 또는 특정 템플릿 매개 변수 중 하나를 사용 하 여 합니다.  
  
```cpp  
// C2248_template.cpp 
// compile with: cl /EHsc /W4 C2248_template.cpp 
template<class T>  
void f(T t) {  
    t.i;   // C2248  
}  
  
struct S {  
private:  
    int i;  
  
public:  
    S() {}  
    friend void f(S);   // refer to the non-template function void f(S)  
    // To fix, comment out the previous line and
    // uncomment the following line.  
    // friend void f<S>(S);  
};  
  
int main() {  
    S s;  
    f<S>(s);  
}  
```  
  
클래스를 클래스의 범위에서 friend 선언을 볼 수 없는 경우와 클래스의 friend를 선언 하려고 하면 때 C2248 노출 하는 또 다른 규칙에 따라 문제 표시 합니다. 이 문제를 해결 하려면 friend로 선언 바깥쪽 클래스입니다.  
  
```cpp  
// C2248_enclose.cpp  
// compile with: cl /W4 /c C2248_enclose.cpp  
class T {  
    class S {  
        class E {};  
    };  
    friend class S::E;   // C2248  
};  
  
class A {  
    class S {  
        class E {};  
        friend class A;  // grant friendship to enclosing class  
    };  
    friend class S::E;   // OK  
};  
```
