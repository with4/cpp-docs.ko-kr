---
title: "형식 특성 (c + + 구성 요소 확장명)에 대 한 컴파일러 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __is_simple_value_class
- __has_trivial_destructor
- __has_assign
- __is_union
- __is_class
- __is_abstract
- __has_trivial_assign
- __has_virtual_destructor
- __is_ref_array
- __is_base_of
- __has_copy
- __is_polymorphic
- __has_nothrow_constructor
- __is_ref_class
- __is_delegate
- __is_convertible_to
- __is_value_class
- __is_interface_class
- __has_nothrow_copy
- __is_sealed
- __has_trivial_constructor
- __has_trivial_copy
- __is_enum
- __has_nothrow_assign
- __has_finalizer
- __is_empty
- __is_pod
- __has_user_destructor
dev_langs:
- C++
helpviewer_keywords:
- __is_class keyword [C++]
- __is_pod keyword [C++]
- __is_delegate keyword [C++]
- __is_value_class keyword [C++]
- __has_copy keyword [C++]
- __has_nothrow_copy keyword [C++]
- __is_interface_class keyword [C++]
- __is_sealed keyword [C++]
- __is_convertible_to keyword [C++]
- __is_ref_class keyword [C++]
- __has_trivial_copy keyword [C++]
- __has_user_destructor keyword [C++]
- __is_abstract keyword [C++]
- __is_empty keyword [C++]
- __has_trivial_assign keyword [C++]
- __has_nothrow_constructor keyword [C++]
- __is_ref_array keyword [C++]
- __is_base_of keyword [C++]
- __has_nothrow_assign keyword [C++]
- __has_virtual_destructor keyword [C++]
- __has_finalizer keyword [C++]
- __is_union keyword [C++]
- __has_assign keyword [C++]
- __has_trivial_destructor keyword [C++]
- __is_polymorphic keyword [C++]
- __is_enum keyword [C++]
- __is_simple_value_class keyword [C++]
- __has_trivial_constructor keyword [C++]
ms.assetid: cd440630-0394-48c0-a16b-1580b6ef5844
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c069645e91d9d895309f00c5f39ddda950084e07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-support-for-type-traits-c-component-extensions"></a>형식 특성에 대한 컴파일러 지원(C++ 구성 요소 확장명)
컴파일러 지원 *특성 입력*, 컴파일 타임에 형식의 다양 한 특성을 나타내는입니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 **주의**  
  
 형식 특성은 라이브러리를 작성하는 프로그래머에게 특히 유용합니다.  
  
 다음 목록에는 컴파일러에서 지 원하는 형식 특성을 포함 합니다. 모든 형식 특성은 형식 특성의 이름에 지정된 조건이 충족되지 않을 경우 `false`를 반환합니다.  
  
 (다음 목록에 코드 예제가 작성만 C + + /cli CLI 합니다. 그러나 해당 형식 특성은 달리 지정되지 않은 경우 [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)]에서도 지원됩니다. , "플랫폼 형식" 용어 Windows 런타임 형식 또는 공용 언어 런타임 형식입니다.)  
  
-   `__has_assign(` `type` `)`  
  
     플랫폼 또는 네이티브 형식에 복사 할당 연산자가 있으면 true를 반환합니다.  
  
    ```  
  
    ref struct R {  
    void operator=(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_assign(R));  
    }  
  
    ```  
  
-   `__has_copy(` `type` `)`  
  
     플랫폼 또는 네이티브 형식에 복사 생성자가 있으면 true를 반환합니다.  
  
    ```  
  
    ref struct R {  
    R(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_copy(R));  
    }  
  
    ```  
  
-   `__has_finalizer(` `type` `)`  
  
     ([!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)]에서는 지원되지 않음) CLR 형식에 종료자가 있으면 true를 반환합니다. 참조 [소멸자 및 종료자에서 하는 방법: 클래스 및 구조체 정의 및 사용 (C + + /cli CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) 자세한 정보에 대 한 합니다.  
  
    ```  
  
    using namespace System;  
    ref struct R {  
    ~R() {}  
    protected:  
    !R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_finalizer(R));  
    }  
  
    ```  
  
-   `__has_nothrow_assign(` `type` `)`  
  
     복사 할당 연산자에 빈 예외 사양이 있으면 true를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    void operator=(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_constructor(` `type` `)`  
  
     기본 생성자에 빈 예외 사양이 있으면 true를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S() throw() {}  
    };  
  
    int main() {  
    __has_nothrow_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_copy(` `type` `)`  
  
     복사 생성자에 빈 예외 사양이 있으면 true를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_assign(` `type` `)`  
  
     형식에 컴파일러에서 생성된 trivial 할당 연산자가 있으면 true를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_constructor(` `type` `)`  
  
     형식에 컴파일러에서 생성된 trivial 생성자가 있으면 true를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_copy(` `type` `)`  
  
     형식에 컴파일러에서 생성된 trivial 복사 생성자가 있으면 true를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_destructor(` `type` `)`  
  
     형식에 컴파일러에서 생성된 trivial 소멸자가 있으면 true를 반환합니다.  
  
    ```  
  
    // has_trivial_destructor.cpp  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_user_destructor(` `type` `)`  
  
     플랫폼 또는 네이티브 형식에 사용자가 선언한 소멸자가 있으면 true를 반환합니다.  
  
    ```  
  
    // has_user_destructor.cpp  
  
    using namespace System;  
    ref class R {  
    ~R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_user_destructor(R));  
    }  
  
    ```  
  
-   `__has_virtual_destructor(` `type` `)`  
  
     형식에 가상 소멸자가 있으면 true를 반환합니다.  
  
     `__has_virtual_destructor`는 플랫폼 형식에 대해서도 작동하며, 플랫폼 형식의 모든 사용자 정의 소멸자는 가상 소멸자입니다.  
  
    ```  
  
    // has_virtual_destructor.cpp  
    #include <stdio.h>  
    struct S {  
    virtual ~S() {}  
    };  
  
    int main() {  
    __has_virtual_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_abstract(` `type` `)`  
  
     형식이 추상 형식이면 true를 반환합니다. 네이티브 추상 형식에 대 한 자세한 내용은 참조 하십시오. [추상](../windows/abstract-cpp-component-extensions.md)합니다.  
  
     `__is_abstract`는 플랫폼 형식에 대해서도 작동합니다. 하나 이상의 멤버가 있는 인터페이스는 하나 이상의 추상 멤버가 있는 참조 형식과 마찬가지로 추상 형식입니다. 추상 플랫폼 형식에 대 한 자세한 내용은 참조 하세요. [추상 클래스](../cpp/abstract-classes-cpp.md)  
  
    ```  
  
    // is_abstract.cpp  
    #include <stdio.h>  
    struct S {  
    virtual void Test() = 0;  
    };  
  
    int main() {  
    __is_abstract(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_base_of(` `base` `,` `derived` `)`  
  
     첫 번째 형식이 두 번째 형식의 기본 클래스이거나 두 형식이 같으면 true를 반환합니다.  
  
     `__is_base_of`는 플랫폼 형식에 대해서도 작동합니다. 예를 들어 true를 반환 합니다 첫 번째 형식이 [인터페이스 클래스](../windows/interface-class-cpp-component-extensions.md) 및 두 번째 형식이 인터페이스를 구현 합니다.  
  
    ```  
  
    // is_base_of.cpp  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    __is_base_of(S, T) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_base_of(S, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_class(` `type` `)`  
  
     형식이 네이티브 클래스 또는 구조체이면 true를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_class(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_convertible_to(` `from` `,`  `to` `)`  
  
     첫 번째 형식을 두 번째 형식으로 변환할 수 있으면 true를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    S * s = new S;  
    T * t = new T;  
    s = t;  
    __is_convertible_to(T, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_delegate(` `type` `)`  
  
     `type`이 대리자이면 true를 반환합니다. 자세한 내용은 참조 [대리자 (c + + 구성 요소 확장명)](../windows/delegate-cpp-component-extensions.md)합니다.  
  
    ```  
  
    delegate void MyDel();  
    int main() {  
    System::Console::WriteLine(__is_delegate(MyDel));  
    }  
  
    ```  
  
-   `__is_empty(` `type` `)`  
  
     형식에 인스턴스 데이터 멤버가 없으면 true를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    int Test() {}  
    static int i;  
    };  
    int main() {  
    __is_empty(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_enum(` `type` `)`  
  
     형식이 네이티브 열거형이면 true를 반환합니다.  
  
    ```  
  
    // is_enum.cpp  
    #include <stdio.h>  
    enum E { a, b };  
  
    struct S {  
    enum E2 { c, d };  
    };  
  
    int main() {  
    __is_enum(E) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_enum(S::E2) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_interface_class(` `type` `)`  
  
     플랫폼 인터페이스가 전달되면 true를 반환합니다. 자세한 내용은 참조 [인터페이스 클래스](../windows/interface-class-cpp-component-extensions.md)합니다.  
  
    ```  
  
    // is_interface_class.cpp  
  
    using namespace System;  
    interface class I {};  
    int main() {  
    Console::WriteLine(__is_interface_class(I));  
    }  
  
    ```  
  
-   `__is_pod(` `type` `)`  
  
     형식이 생성자가 없거나 전용 또는 보호된 비정적 멤버이고, 기본 클래스가 없고, 가상 함수가 없는 클래스 또는 공용 구조체이면 true를 반환합니다. POD에 대한 자세한 내용은 C++ 표준, 섹션 8.5.1/1, 9/4 및 3.9/10을 참조하세요.  
  
     `__is_pod`는 기본 형식에 대해 false를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_pod(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_polymorphic(` `type` `)`  
  
     네이티브 형식에 가상 함수가 있으면 true를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    virtual void Test(){}  
    };  
  
    int main() {  
    __is_polymorphic(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_ref_array(` `type` `)`  
  
     플랫폼 배열이 전달되면 true를 반환합니다. 자세한 내용은 참조 [배열](../windows/arrays-cpp-component-extensions.md)합니다.  
  
    ```  
  
    using namespace System;  
    int main() {  
    array<int>^ x = gcnew array<int>(10);  
    Console::WriteLine(__is_ref_array(array<int>));  
    }  
  
    ```  
  
-   `__is_ref_class(` `type` `)`  
  
     참조 클래스가 전달되면 true를 반환합니다. 사용자 정의 참조 형식에 대 한 자세한 내용은 참조 하십시오. [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)합니다.  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    int main() {  
    Console::WriteLine(__is_ref_class(Buffer));  
    Console::WriteLine(__is_ref_class(R));  
    }  
  
    ```  
  
-   `__is_sealed(` `type` `)`  
  
     sealed로 표시된 플랫폼 또는 네이티브 형식이 전달되면 true를 반환합니다. 자세한 내용은 참조 [봉인](../windows/sealed-cpp-component-extensions.md)합니다.  
  
    ```  
  
    ref class R sealed{};  
    int main() {  
    System::Console::WriteLine(__is_sealed(R));  
    }  
  
    ```  
  
-   `__is_simple_value_class(` `type` `)`  
  
     가비지 수집 힙에 대한 참조가 없는 값 형식이 전달되면 true를 반환합니다. 사용자 정의 값 형식에 대 한 자세한 내용은 참조 하십시오. [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)합니다.  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    value struct V {};  
    value struct V2 {  
    R ^ r;   // not a simnple value type  
    };  
  
    int main() {  
    Console::WriteLine(__is_simple_value_class(V));  
    Console::WriteLine(__is_simple_value_class(V2));  
    }  
  
    ```  
  
-   `__is_union(` `type` `)`  
  
     형식이 공용 구조체이면 true를 반환합니다.  
  
    ```  
  
    #include <stdio.h>  
    union A {  
    int i;  
    float f;  
    };  
  
    int main() {  
    __is_union(A) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_value_class(` `type` `)`  
  
     값 형식이 전달되면 true를 반환합니다. 사용자 정의 값 형식에 대 한 자세한 내용은 참조 하십시오. [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)합니다.  
  
    ```  
  
    value struct V {};  
  
    int main() {  
    System::Console::WriteLine(__is_value_class(V));  
    }  
  
    ```  
  
## <a name="windows-runtime"></a>Windows 런타임  
 **주의**  
  
 `__has_finalizer(` *형식* `)` 형식 특성에는이 플랫폼에서 종료자를 지원 하지 않으므로 지원 되지 않습니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 **주의**  
  
 (이 기능에는 플랫폼별 설명이 없습니다.)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 코드 예제에서는 클래스 템플릿을 사용 하 여에 대 한 컴파일러 형식 특성을 노출 하는 방법을 보여 줍니다.는 **/clr** 컴파일입니다. 자세한 내용은 참조 [Windows 런타임 및 관리 되는 템플릿](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)합니다.  
  
```  
// compiler_type_traits.cpp  
// compile with: /clr  
using namespace System;  
  
template <class T>  
ref struct is_class {  
   literal bool value = __is_ref_class(T);  
};  
  
ref class R {};  
  
int main () {  
   if (is_class<R>::value)  
      Console::WriteLine("R is a ref class");  
   else  
      Console::WriteLine("R is not a ref class");  
}  
```  
  
 **출력**  
  
```Output  
R is a ref class  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)