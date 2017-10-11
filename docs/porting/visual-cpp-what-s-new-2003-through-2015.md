---
title: "Visual C++ 2003 ~ 2015의 새로운 기능 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c4afde6f-3d75-40bf-986f-be57e3818e26
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: 3c1955bece0c8cdadb4a151ee06fa006402666a4
ms.openlocfilehash: 7995451c0c89fbef55bd96291978775f89932f3b
ms.contentlocale: ko-kr
ms.lasthandoff: 06/08/2017

---
# <a name="visual-c-what39s-new-2003-through-2015"></a>Visual C++ 2003 ~ 2015의 새로운 기능

**참고** Visual Studio 2017에 대한 자세한 내용은 [Visual Studio 2017의 Visual C++에 대한 새로운 기능](../what-s-new-for-visual-cpp-in-visual-studio.md) 및 [Visual Studio 2017의 Visual C++에서 규칙 향상](../cpp-conformance-improvements-2017.md)을 참조하세요.

Visual C++ 2015 이상 버전에서는 컴파일러 규칙 개선 작업이 진행 중이므로 컴파일러에서 기존 소스 코드를 인식하는 방식이 변경될 수 있습니다. 이로 인해 빌드 중 새로운 오류 또는 다른 오류가 발생하거나, 이전에 빌드되어 올바르게 실행되는 것처럼 보이는 코드가 다르게 동작할 수도 있습니다.  
  
 다행히 이러한 차이는 대부분의 소스 코드에 거의 또는 전혀 영향을 주지 않으며, 차이를 해결하기 위해 소스 코드 변경이나 기타 변경이 필요한 경우에도 대체로 간단히 처리할 수 있는 사소한 수정입니다. 이전에는 허용되는 소스 코드였지만 변경해야 할 수 있는 코드*(이전)* 및 수정 코드*(이후)*의 많은 예가 포함되어 있습니다.  
  
 이러한 차이가 소스 코드나 다른 빌드 아티팩트에 영향을 줄 수도 있지만 Visual C++ 버전 업데이트 간의 이진 호환성에는 영향을 주지 않습니다. 보다 심각한 종류의 변경인 *주요 변경 내용*은 이진 호환성에 영향을 줄 수 있지만 이러한 종류의 이진 호환성 중단은 Visual C++의 주 버전 간에만 발생합니다. 예를 들어 Visual C++ 2013과 Visual C++ 2015 간에 발생합니다. Visual C++ 2013과 Visual C++ 2015 사이에 발생한 주요 변경 내용에 대한 자세한 내용은 [Visual C++ 변경 기록 2003 - 2015](../porting/visual-cpp-change-history-2003-2015.md)를 참조하세요.  
  
-   [Visual C++ 2015의 규칙 향상](#VS_RTM)  
  
-   [업데이트 1의 규칙 향상](#VS_Update1)  
  
-   [업데이트 2의 규칙 향상](#VS_Update2)  
  
-   [업데이트 3의 규칙 향상](#VS_Update3)  
  
##  <a name="VS_RTM"></a> Visual C++ 2015의 규칙 향상  
  
-   /Zc:forScope- 옵션  
  
     **/Zc:forScope-** 컴파일러 옵션은 사용되지 않으므로 이후 릴리스에서 제거될 예정입니다.  
  
    ```  
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release  
    ```  
  
     옵션은 대개 표준에 따라 범위를 벗어나야 하는 지점 뒤에서 루프 변수를 사용하는 비표준 코드를 허용하려고 사용됩니다. /Za를 사용하지 않으면 루프 끝에 for 루프 변수를 항상 사용할 수 있으므로 /Za 옵션으로 컴파일할 경우에만 필요합니다. 표준 준수가 중요하지 않으면(예: 코드가 다른 컴파일러에 이식 가능하지 않은 경우) /Za 옵션을 해제하거나 언어 확장 사용 안 함 속성을 아니요로 설정할 수 있습니다. 이식 가능한 표준 규격 코드를 작성해야 하면 변수의 선언을 루프 외부 지점으로 이동하여 표준을 따르도록 코드를 다시 작성해야 합니다.  
  
    ```  
    // zc_forScope.cpp  
    // compile with: /Zc:forScope- /Za  
    // C2065 expected  
    int main() {  
       // Uncomment the following line to resolve.  
       // int i;  
       for (int i =0; i < 1; i++)  
          ;  
       i = 20;   // i has already gone out of scope under /Za  
    }  
    ```  
  
-   **/Zg 컴파일러 옵션**  
  
     /Zg 컴파일러 옵션(함수 프로토타입 생성)은 더 이상 사용할 수 없습니다. 이 컴파일러 옵션은 이미 사용되지 않습니다.  
  
-   mstest.exe를 사용하여 명령줄에서 C++/CLI에 대한 단위 테스트를 더 이상 실행할 수 없습니다. 대신에 vstest.console.exe를 사용하세요. [VSTest.Console.exe 명령줄 옵션](/devops-test-docs/test/vstest-console-exe-command-line-options)을 참조하세요.  
  
-   **mutable 키워드**  
  
     이전에 오류 없이 컴파일했던 위치에서 `mutable` 저장소 클래스 지정자가 더 이상 허용되지 않습니다. 현재 컴파일러에서는 오류 C2071(저장소 클래스가 잘못되었습니다.)을 표시합니다. 표준에 따라 mutable 지정자는 클래스 데이터 멤버의 이름에만 적용되고 const 또는 static으로 선언된 이름과 참조 멤버에는 적용할 수 없습니다.  
  
     예를 들어, 다음 코드를 고려하세요.  
  
    ```  
    struct S {  
        mutable int &r;  
    };  
    ```  
  
     이전 Visual C++ 컴파일러 버전에서는 이를 허용했으나 현재 컴파일러에서는 다음 오류를 표시합니다.  
  
    ```Output  
    error C2071: 'S::r': illegal storage class  
    ```  
  
     오류를 수정하려면 중복 mutable 키워드를 제거하세요.  
  
-   **char_16_t 및 char32_t**  
  
     `char16_t` 또는 `char32_t` 형식은 현재 기본 제공으로 처리되므로 typedef에서 이들 형식을 별칭으로 더 이상 사용할 수 없습니다. 사용자와 라이브러리 작성자가 char16_t 및 char32_t를 각각 uint16_t 및 uint32_t의 별칭으로 정의하는 것이 일반적이었습니다.  
  
    ```  
    #include <cstdint>  
  
    typedef uint16_t char16_t; //C2628  
    typedef uint32_t char32_t; //C2628  
  
    int main(int argc, char* argv[])  
    {  
    uint16_t x = 1; uint32_t y = 2;  
    char16_t a = x;   
    char32_t b = y;   
    return 0;  
    }  
    ```  
  
     코드를 업데이트하려면 typedef 선언을 제거하고 이들 이름과 충돌하는 다른 식별자의 이름을 바꿉니다.  
  
-   **비형식 템플릿 매개 변수**  
  
     이제는 비형식 템플릿 매개 변수가 포함된 특정 코드에 명시적 템플릿 인수를 제공하면 형식 호환성 검사가 정확하게 수행됩니다. 예를 들어 다음 코드는 이전 Visual C++ 버전에서는 오류 없이 컴파일되었습니다.  
  
    ```  
    struct S1  
    {  
    void f(int);  
    void f(int, int);  
    };  
  
    struct S2  
    {  
    template <class C, void (C::*Function)(int) const> void f() {}  
    };  
  
    void f()  
    {  
    S2 s2;  
    s2.f<S1, &S1::f>();  
    }  
  
    ```  
  
     템플릿 매개 변수 형식이 템플릿 인수와 일치하지 않기 때문에 현재 컴파일러에서 제대로 오류를 표시합니다. 매개 변수는 const 멤버의 포인터이나 f 함수는 비const입니다.  
  
    ```Output  
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'  
    ```  
  
     코드에서 이 오류를 해결하려면 사용하는 템플릿 인수 형식이 템플릿 매개 변수의 선언된 형식과 일치해야 합니다.  
  
-   **__declspec(align)**  
  
     컴파일러가 함수에서 `__declspec(align)` 을 더 이상 허용하지 않습니다. 이는 항상 무시되었지만 현재는 컴파일러 오류가 생성됩니다.  
  
    ```  
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations  
    ```  
  
     이 문제를 수정하려면 함수 선언에서 `__declspec(align)` 을 제거합니다. 아무런 영향이 없으므로 제거해도 아무것도 변경되지 않습니다.  
  
-   **예외 처리**  
  
     예외 처리에 대한 몇 가지 변경 내용이 있습니다. 먼저 예외 개체는 복사 가능하거나 이동 가능해야 합니다. 다음 코드는 [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서 컴파일되었지만 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서는 컴파일되지 않습니다.  
  
    ```  
    struct S {  
    public:  
        S();  
    private:  
        S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
  
    ```  
  
     문제는 복사 생성자가 private이라는 점이므로 일반적인 예외 처리 과정으로는 개체를 복사할 수 없습니다. 복사 생성자가 `explicit`로 선언될 경우에도 마찬가지입니다.  
  
    ```  
    struct S {  
        S();  
        explicit S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
  
    ```  
  
     코드를 업데이트하려면 예외 개체에 대한 복사 생성자가 public이고 `explicit`로 표시되지 않아야 합니다.  
  
     값으로 예외를 catch하려면 예외 개체가 복사 가능해야 합니다. 다음 코드는 [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서 컴파일되었지만 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서는 컴파일되지 않습니다.  
  
    ```  
    struct B {  
    public:  
        B();  
    private:  
        B(const B &);  
    };  
  
    struct D : public B {  
    };  
  
    int main()  
    {  
        try  
        {  
        }  
        catch (D d) // error  
        {  
        }  
    }  
  
    ```  
  
     참조에 대한 `catch` 의 매개 변수 형식을 변경하여 이 문제를 해결할 수 있습니다.  
  
    ```  
    catch(D& d)  
    {  
    }  
    ```  
  
-   **매크로 뒤의 문자열 리터럴**  
  
     현재 컴파일러는 사용자 정의 리터럴을 지원합니다. 따라서 중간 공백 없이 매크로 뒤의 문자열 리터럴은 오류나 예기치 않은 결과를 생성할 수 있는 사용자 정의 리터럴로 해석됩니다. 예를 들어 이전 컴파일러에서는 다음 코드가 성공적으로 컴파일되었습니다.  
  
    ```  
    #define _x "there"  
    char* func() {  
        return "hello"_x;  
    }  
    int main()  
    {  
        char * p = func();  
        return 0;  
    }  
    ```  
  
     컴파일러에서 이 코드는 매크로 뒤의 문자열 리터럴 "hello"로 해석되고 “there”로 확장되었고 두 문자열 리터럴은 하나로 연결되었습니다. [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서 컴파일러는 이 코드를 사용자 정의 리터럴로 해석하지만 일치하는 사용자 정의 리터럴 _x가 정의되지 않았으므로 오류가 발생합니다.  
  
    ```  
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found  
    note: Did you forget a space between the string literal and the prefix of the following string literal?  
  
    ```  
  
     이 문제를 수정하려면 문자열 리터럴과 매크로 사이에 공백을 추가합니다.  
  
-   **인접 문자열 리터럴**  
  
     이전과 비슷하게 문자열 구문 분석의 관련 변경 내용 때문에 공백이 없는 인접 문자열 리터럴(전각 또는 반각 문자 문자열 리터럴)은 이전 Visual C++ 릴리스에서 하나의 연결된 문자열로 해석되었습니다. [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서는 현재 두 문자열 사이에 공백을 추가해야 합니다. 예를 들어 다음 코드를 변경해야 합니다.  
  
    ```  
    char * str = "abc""def";  
    ```  
  
     두 문자열 사이에 공백을 추가하면 됩니다.  
  
    ```  
    char * str = "abc" "def";  
    ```  
  
-   **Placement new 및 delete**  
  
     delete 연산자는 C++14 표준을 준수하도록 변경되었습니다. 표준 변경에 대한 자세한 내용은 [C++ 크기 지정된 할당 해제](http://isocpp.org/files/papers/n3778.html)(영문)를 참조하세요. 변경을 통해 size 매개 변수를 사용하는 전역 delete 연산자의 형식이 추가됩니다. 주요 변경 내용에 따르면 이전에는 placement new 연산자와 일치하도록 같은 서명으로 delete 연산자를 사용하면 placement new가 사용된 지점에서 컴파일러 오류(C2956)가 발생했습니다. 이 지점은 컴파일러가 해당하는 일치 delete 연산자를 식별하려고 하는 코드의 위치이기 때문입니다.  
  
     `void operator delete(void *, size_t)` 함수는 C++11의 placement new 함수 "void \* 연산자 new(size_t, size_t)"와 일치하는 placement delete 연산자였습니다. C++14 크기 지정된 할당 해제를 사용하면 이 delete 함수는 현재 *usual deallocation 함수* (전역 delete 연산자)입니다. 표준에 따르면 placement new를 사용하여 해당하는 delete 함수를 조회하고 usual deallocation 함수를 찾으면 프로그램에 잘못된 형식이 사용됩니다.  
  
     예를 들어 코드에서 placement new 및 placement delete를 둘 다 정의한다고 가정합니다.  
  
    ```  
    void * operator new(std::size_t, std::size_t);  
    void operator delete(void*, std::size_t) noexcept;  
  
    ```  
  
     정의한 placement delete 연산자와 새 전역 크기 지정된 delete 연산자 간에 함수 서명이 일치하기 때문에 문제가 발생합니다. placement new 및 delete 연산자에 대해 size_t 이외의 다른 연산자를 사용할 수 있는지를 고려하세요.  size_t typedef의 형식은 컴파일러에 따라 결정되고 Visual C++에서는 부호 없는 int에 대한 typedef입니다. 이 문제를 해결하려면 다음과 같은 열거된 형식을 사용하는 것이 좋습니다.  
  
    ```  
    enum class my_type : size_t {};  
  
    ```  
  
     그다음에 size_t 대신 이 형식을 두 번째 인수로 사용하도록 placement new 및 delete의 정의를 변경합니다. placement new에 대한 호출을 업데이트하여 새 형식을 전달하고(예: `static_cast<my_type>` 을 사용하여 정수 값에서 변환) new 및 delete의 정의를 업데이트하여 다시 정수 형식으로 캐스팅해야 합니다. 여기에 열거형을 사용할 필요가 없고 size_t 멤버가 있는 클래스 형식도 사용할 수 있습니다.  
  
     또 다른 솔루션은 placement new를 함께 제거하는 것입니다. 코드에서 placement new를 사용하여 placement 인수가 할당되거나 삭제되는 개체 크기와 같은 메모리 풀을 구현하면 사용자 지정 메모리 풀 코드를 바꾸는 데는 크기 지정된 할당 해제 기능이 적합할 수 있고, placement 함수를 제거하고 placement 대신에 인수가 두 개인 delete 연산자만 사용할 수 있습니다.  
  
     코드를 바로 업데이트하지 않으려면 컴파일러 옵션 /Zc:sizedDealloc-를 사용하여 이전 동작으로 되돌릴 수 있습니다. 이 옵션을 사용하면 인수가 두 개인 delete 함수가 존재하지 않으므로 placement delete 연산자와 충돌하지 않습니다.  
  
-   **공용 구조체 데이터 멤버**  
  
     공용 구조체의 데이터 멤버는 더 이상 참조 형식을 포함할 수 없습니다. [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서는 다음 코드가 성공적으로 컴파일되었지만 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서는 오류가 발생합니다.  
  
    ```  
    union U1 {  
        const int i;  
    };  
    union U2 {  
       int &i;  
    };  
    union U3 {  
        struct {int &i;};  
    };  
    ```  
  
     앞의 코드에서 발생하는 오류는 다음과 같습니다.  
  
    ```Output  
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type  
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type  
    ```  
  
     이 문제를 해결하려면 참조 형식을 포인터 또는 값으로 변경합니다. 형식을 포인터로 변경하려면 공용 구조체 필드를 사용하는 코드를 변경해야 합니다. 코드를 값으로 변경하면 공용 구조체에 저장된 데이터가 변경되며, union 형식의 필드는 같은 메모리를 공유하므로 이 변경이 다른 필드에 영향을 미칩니다. 값 크기에 따라 공용 구조체 크기도 변경할 수 있습니다.  
  
-   현재 익명 공용 구조체는 표준을 더 준수합니다. 이전 컴파일러 버전에서는 익명 공용 구조체에 대한 명시적 생성자 및 소멸자를 생성했습니다. 이 기능은 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서 삭제되었습니다.  
  
    ```  
    struct S {  
      S();  
     };  
  
     union {  
      struct {  
       S s;  
      };  
     } u; // C2280  
    ```  
  
     앞의 코드는 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서 다음 오류를 생성합니다.  
  
    ```  
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function  
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here  
    ```  
  
     이 문제를 해결하려면 생성자 및/또는 소멸자의 정의를 제공하세요.  
  
    ```  
    struct S {  
    // Provide a default constructor by adding an empty function body.  
    S() {}   
    };  
  
    union {  
    struct {  
    S s;  
    };  
    } u;  
    ```  
  
-   **익명 구조체가 있는 공용 구조체**  
  
     공용 구조체에서 익명 구조체 멤버의 런타임 동작이 표준을 준수하도록 변경되었습니다. 해당 공용 구조체가 생성될 때 공용 구조체의 익명 구조체 멤버에 대한 생성자가 더 이상 암시적으로 호출되지 않습니다. 또한 공용 구조체가 범위를 벗어날 때 공용 구조체의 익명 구조체 멤버에 대한 소멸자가 더 이상 암시적으로 호출되지 않습니다. 소멸자가 있는 명명된 구조체 S 멤버가 포함된 익명 구조체가 공용 구조체 U에 들어 있는 다음 코드를 고려하세요.  
  
    ```  
    #include <stdio.h>  
    struct S {  
        S() { printf("Creating S\n"); }  
        ~S(){ printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
        S s;  
    };  
        U() {}  
        ~U(){}  
    };  
  
    void f()  
    {  
        U u;  
        // Destructor implicitly called here.  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서 S에 대한 생성자는 공용 구조체가 생성될 때 호출되고 S에 대한 소멸자는 f 함수의 스택이 정리될 때 호출됩니다. 그러나 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서는 생성자와 소멸자가 호출되지 않습니다. 컴파일러에서 이 동작 변경에 대해 경고를 표시합니다.  
  
    ```Output  
    warning C4587: 'U::s': behavior change: constructor is no longer implicitly calledwarning C4588: 'U::s': behavior change: destructor is no longer implicitly called  
    ```  
  
     원래 동작을 복원하려면 익명 구조체에 이름을 지정합니다. 익명이 아닌 구조체의 런타임 동작은 컴파일러 버전과 관계없이 동일합니다.  
  
    ```  
    #include <stdio.h>  
  
    struct S {  
        S() { printf("Creating S.\n"); }  
        ~S() { printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
            S s;  
        } namedStruct;  
        U() {}  
        ~U() {}  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     또는 생성자 및 소멸자 코드를 새 함수로 이동하고 공용 구조체에 대한 생성자 및 소멸자에서 이들 함수에 호출을 추가하세요.  
  
    ```  
    #include <stdio.h>  
  
    struct S {  
        void Create() { printf("Creating S.\n"); }  
        void Destroy() { printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
            S s;  
        };  
        U() { s.Create();  }  
        ~U() { s.Destroy(); }  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
    char s[1024];  
    printf("Press any key.\n");  
    gets_s(s);  
    return 0;  
    }  
    ```  
  
-   **템플릿 확인**  
  
     템플릿의 이름 확인에 대한 변경 내용이 있습니다. C++에서 이름을 확인할 후보를 고려할 때 잠재적인 일치 항목으로 고려 중인 하나 이상의 이름에서 잘못된 템플릿 인스턴스화가 생성될 수 있습니다. 보통 이들 잘못된 인스턴스화 때문에 컴파일러 오류가 발생하지는 않습니다. 이 원칙을 SFINAE(Substitution Failure Is Not An Error)라고 합니다.  
  
     현재 SFINAE에 따라 컴파일러가 클래스 템플릿의 특수화를 인스턴스화해야 하면 이 프로세스 중에 발생하는 오류는 컴파일러 오류입니다. 이전 버전에서는 컴파일러가 해당 오류를 무시합니다. 예를 들어, 다음 코드를 고려하세요.  
  
    ```  
    #include <type_traits>  
  
    template<typename T>  
    struct S  
    {  
    S() = default;  
    S(const S&);  
    S(S&&);  
  
    template<typename U, typename = typename std::enable_if<std::is_base_of<T, U>::value>::type>  
    S(S<U>&&);  
    };  
  
    struct D;  
  
    void f1()  
    {  
    S<D> s1;  
        S<D> s2(s1);  
    }  
  
    struct B  
    {  
    };  
  
    struct D : public B  
    {  
    };  
  
    void f2()  
    {  
    S<D> s1;  
        S<D> s2(s1);  
    }  
  
    ```  
  
     현재 컴파일러로 컴파일할 경우 다음 오류가 발생합니다.  
  
    ```Output  
    type_traits(1110): error C2139: 'D': an undefined class is not allowed as an argument to compiler intrinsic type trait '__is_base_of'  
    ..\t331.cpp(14): note: see declaration of 'D'  
    ..\t331.cpp(10): note: see reference to class template instantiation 'std::is_base_of<T,U>' being compiled  
            with  
            [  
                T=D,  
                U=D  
            ]  
    ```  
  
     이는 is_base_of의 첫 번째 호출 지점에서 'D' 클래스가 아직 정의되지 않았기 때문입니다.  
  
     이 경우 문제를 해결하려면 클래스가 정의될 때까지 이러한 형식 특성을 사용하지 마세요. B 및 D의 정의를 코드 파일의 시작 부분으로 이동하면 오류가 해결됩니다. 정의가 헤더 파일에 있으면 헤더 파일의 include 문 순서를 확인하여 문제가 있는 템플릿이 사용되기 전에 클래스 정의가 컴파일되는지 확인합니다.  
  
-   **복사 생성자**  
  
     [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] 및 Visual Studio 2015에서 컴파일러는 클래스에 사용자 정의 이동 생성자가 있지만 사용자 정의 복사 생성자가 없을 경우 해당 클래스에 대한 복사 생성자를 생성합니다. Dev14에서는 생성된 복사 생성자가 "= delete"로 표시됩니다.  
  
##  <a name="VS_Update1"></a> 업데이트 1의 규칙 향상  
  
-   **개인 가상 기본 클래스 및 간접 상속**  
  
     이전 버전의 컴파일러에서는 파생 클래스에서 *간접적으로 파생된*`private virtual` 기본 클래스의 멤버 함수를 호출할 수 있었습니다. 이 이전 동작은 올바르지 않으며 C++ 표준을 따르지 않습니다. 컴파일러는 이러한 방식으로 작성된 코드를 더 이상 허용하지 않으며, 결과적으로 컴파일러 오류 C2280이 발생합니다.  
  
    ```Output  
    error C2280: 'void *S3::__delDtor(unsigned int)': attempting to reference a deleted function  
    ```  
  
     예제(이전)  
  
    ```cpp  
    class base  
    {  
    protected:  
        base();  
        ~base();  
    };  
  
    class middle: private virtual base {};class top: public virtual middle {};  
  
    void destroy(top *p)  
    {  
        delete p;  //   
    }  
    ```  
  
     예제(이후)  
  
    ```cpp  
    class base;  // as above  
  
    class middle: protected virtual base {};  
    class top: public virtual middle {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
     또는  
  
    ```  
    class base;  // as above  
  
    class middle: private virtual base {};  
    class top: public virtual middle, private virtual bottom {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
-   **오버로드된 operator new 및 operator delete**  
  
     이전 버전의 컴파일러에서는 멤버가 아닌 `operator new` 및 멤버가 아닌 `operator delete` 를 정적으로 선언할 수 있었으며 전역 네임스페이스 이외의 네임스페이스에서 선언할 수 있었습니다.  이 이전 동작은 프로그램에서 프로그래머가 의도한 `new` 또는 `delete` 연산자 구현을 호출하지 않아서 잘못된 자동 런타임 동작이 발생하는 위험을 초래했습니다. 컴파일러는 이러한 방식으로 작성된 코드를 더 이상 허용하지 않으며, 대신 컴파일러 오류 C2323이 발생합니다.  
  
    ```Output  
    error C2323: 'operator new': non-member operator new or delete functions may not be declared static or in a namespace other than the global namespace.  
    ```  
  
     예제(이전)  
  
    ```cpp  
    static inline void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // error C2323  
    ```  
  
     예제(이후)  
  
    ```cpp  
    void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // removed 'static inline'  
    ```  
  
     또한 컴파일러가 특정 진단을 제공하지는 않지만, 인라인 operator new는 잘못된 형식으로 간주됩니다.  
  
-   ***비클래스 형식에서 'operator* type**()'(사용자 정의 변환) 호출  
  
     이전 버전의 컴파일러에서는 'operator *type*()'을 자동으로 무시하면서 비클래스 형식에서 호출할 수 있었습니다. 이 이전 동작으로 잘못된 코드가 자동으로 생성되어 예기치 않은 런타임 동작이 발생하는 위험이 초래되었습니다. 컴파일러는 이러한 방식으로 작성된 코드를 더 이상 허용하지 않으며, 대신 컴파일러 오류 C2228이 발생합니다.  
  
    ```Output  
    error C2228: left of '.operator type' must have class/struct/union  
    ```  
  
     예제(이전)  
  
    ```cpp  
    typedef int index_t;  
  
    void bounds_check(index_t index);  
  
    void login(int column)  
    {  
        bounds_check(column.operator index_t());  // error C2228  
    }  
    ```  
  
     예제(이후)  
  
    ```cpp  
    typedef int index_t;  
  
    void bounds_check(index_t index);  
  
    void login(int column)  
    {  
        bounds_check(column);  // removed cast to 'index_t', 'index_t' is an alias of 'int'  
    }  
    ```  
  
-   **상세 형식 지정자의 중복 typename**  
  
     이전 버전의 컴파일러에서는 상세 형식 지정자에 `typename` 이 허용되었습니다. 이러한 방식으로 작성된 코드는 의미 체계가 잘못되었습니다. 컴파일러는 이러한 방식으로 작성된 코드를 더 이상 허용하지 않으며, 대신 컴파일러 오류 C3406이 발생합니다.  
  
    ```Output  
    error C3406: 'typename' cannot be used in an elaborated type specifier  
    ```  
  
     예제(이전)  
  
    ```cpp  
    template <typename class T>  
    class container;  
    ```  
  
     예제(이후)  
  
    ```cpp  
    template <class T>  // alternatively, could be 'template <typename T>'; 'typename' is not elaborating a type specifier in this case  
    class container;  
    ```  
  
-   **이니셜라이저 목록에서 배열의 형식 추론**  
  
     이전 버전의 컴파일러는 이니셜라이저 목록에서 배열의 형식 추론을 지원하지 않았습니다. 이제 컴파일러가 이러한 형태의 형식 추론을 지원합니다. 결과적으로 이니셜라이저 목록을 사용한 함수 템플릿 호출은 이제 모호하거나 이전 버전의 컴파일러와 다른 오버로드가 선택될 수 있습니다. 이러한 문제를 해결하려면 이제 프로그램에서 프로그래머가 의도한 오버로드를 명시적으로 지정해야 합니다.  
  
     이 새로운 동작으로 오버로드 확인에서 기록 후보와 똑같이 우수한 추가 후보를 고려하게 되는 경우, 호출이 모호해지며 결과적으로 컴파일러에서 컴파일러 오류 C2668이 발생합니다.  
  
    ```Output  
    error C2668: 'function' : ambiguous call to overloaded function.  
    ```  
  
     예제 1: 오버로드된 함수에 대한 호출이 모호합니다(이전).  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(int, Args...)  
    template <typename... Args>  
    void f(int, Args...);  //   
  
    template <int N, typename... Args>  
    void f(const int (&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now considers this call ambiguous, and issues a compiler error  
        f({3});  error C2668: 'f' ambiguous call to overloaded function  
    }  
    ```  
  
     예제 1: 오버로드된 함수에 대한 호출이 모호합니다(이후).  
  
    ```cpp  
    template <typename... Args>  
    void f(int, Args...);  //   
  
    template <int N, typename... Args>  
    void f(const int (&)[N], Args...);  
  
    int main()  
    {  
        // To call f(int, Args...) when there is just one expression in the initializer list, remove the braces from it.  
        f(3);  
    }  
    ```  
  
     이 새로운 동작으로 오버로드 확인에서 기록 후보보다 더 일치되는 추가 후보를 고려하게 되는 경우, 호출이 새 후보로 명확하게 확인되므로 프로그래머가 의도한 것과 다른 프로그램 동작 변경을 초래할 수 있습니다.  
  
     예제 2: 오버로드 확인의 변경(이전)  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(S, Args...)  
    struct S  
    {  
        int i;  
        int j;  
    };  
  
    template <typename... Args>  
    void f(S, Args...);  
  
    template <int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now resolves this call to f(const int (&)[N], Args...) instead  
        f({1, 2});  
    }  
    ```  
  
     예제 2: 오버로드 확인의 변경(이후)  
  
    ```cpp  
    struct S;  // as before  
  
    template <typename... Args>  
    void f(S, Args...);  
  
    template <int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // To call f(S, Args...), perform an explicit cast to S on the initializer list.  
        f(S{1, 2});  
    }  
    ```  
  
-   **switch 문 경고의 복원**  
  
     이전 버전의 컴파일러에서는 `switch` 문과 관련된 기존 경고를 제거했습니다. 이제 이러한 경고가 복원되었습니다. 이제 컴파일러에서 복원된 경고가 발생합니다. 이제 특정 사례(기본 사례 포함)와 관련된 경고가 switch 문의 마지막 줄 대신, 잘못된 사례가 포함된 줄에서 발생합니다. 이제 과거와는 다른 줄에서 해당 경고가 발생하므로 이전에 `#pragma warning(disable:####)` 을 사용하면 표시되지 않았던 경고가 더 이상 의도한 대로 숨겨지지 않을 수 있습니다. 이러한 경고를 의도한 대로 표시하지 않으려면 `#pragma warning(disable:####)` 지시문을 잠재적으로 잘못된 첫 번째 사례 위의 줄로 이동해야 할 수 있습니다. 다음은 복원된 경고입니다.  
  
    ```Output  
    warning C4060: switch statement contains no 'case' or 'default' labels  
    ```  
  
    ```Output  
    warning C4061: enumerator 'bit1' in switch of enum 'flags' is not explicitly handled by a case label  
    ```  
  
    ```Output  
    warning C4062: enumerator 'bit1' in switch of enum 'flags' is not handled  
    ```  
  
    ```Output  
    warning C4063: case 'bit32' is not a valid value for switch of enum 'flags'  
    ```  
  
    ```Output  
    warning C4064: switch of incomplete enum 'flags'  
    ```  
  
    ```Output  
    warning C4065: switch statement contains 'default' but no 'case' labels  
    ```  
  
    ```Output  
    warning C4808: case 'value' is not a valid value for switch condition of type 'bool'  
    ```  
  
    ```Output  
    Warning C4809: switch statement has redundant 'default' label; all possible 'case' labels are given  
    ```  
  
     C4063의 예제(이전)  
  
    ```cpp  
    class settings  
    {  
    public:  
        enum flags  
        {  
            bit0 = 0x1,  
            bit1 = 0x2,  
            ...  
        };  
        ...  
    };  
  
    int main()  
    {  
        auto val = settings::bit1;  
  
        switch (val)  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
        case settings::bit0 | settings::bit1:  // warning C4063  
            break;  
        }  
    };  
    ```  
  
     C4063의 예제(이후)  
  
    ```cpp  
    class settings {...};  // as above  
  
    int main()  
    {  
        // since C++11, use std::underlying_type to determine the underlying type of an enum  
        typedef std::underlying_type<settings::flags>::type flags_t;  
  
        auto val = settings::bit1;  
  
        switch (static_cast<flags_t>(val))  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
        case settings::bit0 | settings::bit1:  // ok  
            break;  
        }  
    };  
    ```  
  
     복원된 다른 경고의 예는 해당 설명서에 제공됩니다.  
  
-   **#include: 경로 이름에 부모 디렉터리 지정자 '..' 사용** (/Wall /WX에만 영향을 줌)  
  
     이전 버전의 컴파일러에서는 `#include` 지시문의 경로 이름에서 부모 디렉터리 지정자('..')의 사용을 검색하지 못했습니다. 이러한 방식으로 작성된 코드는 일반적으로 프로젝트 상대 경로를 부정확하게 사용하여 프로젝트의 외부에 존재하는 헤더를 포함합니다. 이 이전 동작은 프로그램이 프로그래머가 의도한 것과 다른 소스 파일을 포함하여 컴파일되거나 이러한 상대 경로가 다른 빌드 환경으로 이식되지 않는 위험을 초래했습니다. 이제 컴파일러는 이러한 방식으로 작성된 코드를 검색하여 프로그래머에게 알립니다. 그리고 사용하도록 설정된 경우 선택적으로 컴파일러 경고 C4464가 발생합니다.  
  
    ```Output  
    warning C4464: relative include path contains '..'  
    ```  
  
     예제(이전)  
  
    ```cpp  
    #include "..\headers\C4426.h"  // emits warning C4464  
    ```  
  
     예제(이후)  
  
    ```cpp  
    #include "C4426.h"  // add absolute path to 'headers\' to your project's include directories  
    ```  
  
     또한 컴파일러가 특정 진단을 제공하지는 않지만, 프로젝트의 Include 디렉터리를 지정하는 데 부모 디렉터리 지정자("..")를 사용하지 않는 것이 좋습니다.  
  
-   **#pragma optimize()에서 헤더 파일의 끝을 넘어 확장** (/Wall /WX에만 영향을 줌)  
  
     이전 버전의 컴파일러에서는 변환 단위 내에 포함된 헤더 파일을 이스케이프하는 최적화 플래그 설정에 대한 변경 내용을 검색하지 못했습니다. 이제 컴파일러는 이러한 방식으로 작성된 코드를 검색하여 프로그래머에게 알립니다. 그리고 사용하도록 설정된 경우 잘못된 `#include`의 위치에서 선택적으로 컴파일러 경고 C4426이 발생합니다. 이 경고는 변경 내용이 명령줄 인수에 의해 컴파일러에 설정된 최적화 플래그와 충돌하는 경우에만 발생합니다.  
  
    ```Output  
    warning C4426: optimization flags changed after including header, may be due to #pragma optimize()  
    ```  
  
     예제(이전)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
    ...  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  // warning C4426  
    ```  
  
     예제(이후)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
    ...  
    #pragma optimize("", on)  // restores optimization flags set via command-line arguments  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  
    ```  
  
-   **#pragma warning(push)** 과 **#pragma warning(pop)** (/Wall /WX에만 영향을 줌)  
  
     이전 버전의 컴파일러는 다른 소스 파일에서 `#pragma warning(push)` 상태 변경이 `#pragma warning(pop)` 상태 변경과 쌍을 이루는 것(의도되는 경우가 드묾)을 검색하지 못했습니다. 이 이전 동작으로 프로그램이 프로그래머가 의도한 것과 다르게 설정된 경고 집합으로 컴파일되어 잘못된 자동 런타임 동작이 발생하는 위험이 초래됩니다. 이제 컴파일러는 이러한 방식으로 작성된 코드를 검색하여 프로그래머에게 알립니다. 그리고 사용하도록 설정된 경우 일치하는 `#pragma warning(pop)`의 위치에서 선택적으로 컴파일러 경고 C5031이 발생합니다. 이 경고에는 해당 #pragma warning(push)의 위치를 참조하는 참고가 포함되어 있습니다.  
  
    ```Output  
    warning C5031: #pragma warning(pop): likely mismatch, popping warning state pushed in different file  
    ```  
  
     예제(이전)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    ...  
    #pragma warning(pop)  // pops a warning state not pushed in this source file   
    ...  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // leaves #pragma warning(push) 'dangling'  
    ...  
    #include "C5031_part2.h" // matches 'dangling' #pragma warning(push), resulting in warning C5031  
    ...  
  
    ```  
  
     예제(이후)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  // pops the warning state pushed in this source file  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    #pragma warning(push)  // pushes the warning state pushed in this source file  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // #pragma warning state changes are self-contained and independent of other source files or their #include order.  
    ...  
    #include "C5031_part2.h"  
    ...  
  
    ```  
  
     드물긴 하지만 의도적으로 이러한 코드를 작성하는 경우가 있습니다. 이러한 방식으로 작성된 코드는 `#include` 순서의 변경에 민감합니다. 가능한 경우 소스 코드 파일에서 자동으로 포함된 방식으로 경고 상태를 관리하는 것이 좋습니다.  
  
-   **#pragma warning(push) 불일치** (/Wall /WX에만 영향을 줌)  
  
     이전 버전의 컴파일러는 변환 단위의 끝에서 `#pragma warning(push)` 상태 변경 불일치를 검색하지 못했습니다. 이제 컴파일러는 이러한 방식으로 작성된 코드를 검색하여 프로그래머에게 알립니다. 그리고 사용하도록 설정된 경우 일치하지 않는 #pragma warning(push)의 위치에서 선택적으로 컴파일러 경고 C5032가 발생합니다. 이 경고는 변환 단위에 컴파일 오류가 없는 경우에만 발생합니다.  
  
    ```Output  
    warning C5032: detected #pragma warning(push) with no corresponding #pragma warning(pop)  
    ```  
  
     예제(이전)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5032.h ends without #pragma warning(pop)  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without #pragma warning(pop), resulting in warning C5032 on line 1 of C5032.h  
    ```  
  
     예제(이후)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop) // matches #pragma warning (push) on line 1  
    // C5032.h ends  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without unmatched #pragma warning(push)  
    ```  
  
-   **개선된 #pragma warning 상태 추적의 결과로 추가 경고가 발생할 수 있습니다.**  
  
     이전 버전의 컴파일러는 의도된 모든 경고를 발생시키기에는 불충분한 수준으로 #pragma warning 상태 변경을 추적했습니다. 이 동작으로 프로그래머가 의도한 것과 다른 상황에서 특정 경고가 효과적으로 표시되지 않는 위험이 초래됩니다. 이제 컴파일러는 #pragma warning 상태(특히 템플릿 내부의 #pragma warning 상태 변경과 관련된 내용)를 더욱 강력하게 추적하며, 선택적으로 새로운 경고 C5031 및 C5032가 발생합니다. 이러한 경고는 프로그래머가 `#pragma warning(push)` 및 `#pragma warning(pop)`의 의도하지 않은 사용을 찾는 데 도움이 됩니다.  
  
     개선된 #pragma warning 상태 변경 추적의 결과로, 이전에 제대로 표시되지 않은 경고 또는 이전에 잘못 진단된 문제와 관련된 경고가 이제 발생할 수 있습니다.  
  
-   **접근할 수 없는 코드의 개선된 ID**  
  
     C++ 표준 라이브러리의 변경 및 이전 버전의 컴파일러에 비해 향상된 인라인 함수 호출 기능을 통해 컴파일러가 이제 특정 코드에 접근할 수 없음을 증명할 수 있습니다. 이 새로운 동작으로 경고 C4720의 인스턴스가 새로 그리고 더욱 자주 발생할 수 있습니다.  
  
    ```Output  
    warning C4720: unreachable code  
    ```  
  
     최적화 프로세스에서 더 많은 함수 호출을 인라인하거나 중복 코드를 제거하거나 특정 코드에 접근할 수 없는지 확인할 수 있도록 하므로, 이 경고는 대개 최적화를 사용하면서 컴파일할 경우에만 발생할 수 있습니다. 경고 C4720의 새 인스턴스가 특히 [std::find](assetId:///std::find?qualifyHint=False&autoUpgrade=True)의 사용과 관련하여 try/catch 블록에서 자주 발생했음을 관찰했습니다.  
  
     예제(이전)  
  
    ```cpp  
    try   
    {   
        auto iter = std::find(v.begin(), v.end(), 5);   
    }   
    catch(...)   
    {   
        do_something();  // ok   
    }  
    ```  
  
     예제(이후)  
  
    ```cpp  
    try   
    {   
        auto iter = std::find(v.begin(), v.end(), 5);   
    }   
    catch(...)   
    {   
        do_something();  // warning C4702: unreachable code  
    }  
    ```  
  
##  <a name="VS_Update2"></a> 업데이트 2의 규칙 향상  
  
-   **SFINAE 식에 대한 부분 지원으로 인해 추가 경고 및 오류가 발생할 수 있습니다.**  
  
     이전 버전의 컴파일러는 SFINAE 식에 대한 지원 부족으로 `decltype` 지정자 내의 특정 유형의 식을 구문 분석하지 않았습니다. 이 이전 동작은 올바르지 않으며 C++ 표준을 따르지 않습니다. 지속적인 규칙 향상으로 인해 이제 컴파일러는 이러한 식을 구문 분석하고 SFINAE 식에 대한 부분 지원을 합니다. 결과적으로 이제 컴파일러는 이전 버전의 컴파일러가 구문 분석하지 않았던 식에서 경고 및 오류를 발생합니다.  
  
     이 새로운 동작이 아직 선언되지 않은 형식을 포함하는 `decltype` 식을 구문 분석할 때, 컴파일러는 결과적으로 오류 C2039를 발생합니다.  
  
    ```Output  
    error C2039: 'type': is not a member of '`global namespace''  
    ```  
  
     예제 1: 선언되지 않은 형식 사용(이전)  
  
    ```cpp  
    struct s1  
    {  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  // error C2039  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     예제 1(이후)  
  
    ```cpp  
    struct s1  
    {  
      template <typename>  // forward declare s2struct s2;  
  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     이 새로운 동작이 종속 이름이 형식임을 지정하기 위해 필요한 `typename` 키워드 사용이 누락된 `decltype` 식을 구문 분석할 때 컴파일러는 컴파일러 오류 C2923과 함께 컴파일러 경고 C4346을 발생합니다.  
  
    ```Output  
    warning C4346: 'S2<T>::Type': dependent name is not a type  
    ```  
  
    ```Output  
    error C2923: 's1': 'S2<T>::Type' is not a valid template type argument for parameter 'T'  
    ```  
  
     예제 2: 종속 이름이 형식이 아님(이전)  
  
    ```cpp  
    template <typename T>  
    struct s1  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    struct s2  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<S2<T>::type>::type>()));  // warning C4346, error C2923  
    };  
    ```  
  
     예제 2(이후)  
  
    ```cpp  
    template <typename T> struct s1 {...};  // as above  
    template <typename T> struct s2 {...};  // as above  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<typename S2<T>::type>::type>()));  
    };  
    ```  
  
-   `volatile` **멤버 변수가 암시적으로 정의된 생성자와 대입 연산자를 막음**  
  
     이전 버전의 컴파일러는 `volatile` 멤버 변수가 있는 클래스가 기본 복사/이동 생성자 및 기본 복사 대입 연산자를 자동으로 생성하도록 허용했습니다. 이 이전 동작은 올바르지 않으며 C++ 표준을 따르지 않습니다. 이제 컴파일러는 volatile 멤버 변수가 있는 클래스는 특수한 생성자 및 대입 연산자가 있는 것으로 간주하여 이러한 연산자의 기본 구현이 자동으로 생성되는 것을 막습니다.  이러한 클래스가 공용 구조체(또는 클래스 내의 익명 공용 구조체)의 멤버이면 공용 구조체(또는 익명 공용 구조체를 포함하는 클래스)의 복사/이동 생성자 및 복사/이동 대입 연산자는 삭제된 것으로 암시적으로 정의됩니다. 명시적으로 정의하지 않고 공용 구조체(또는 익명 공용 구조체를 포함하는 클래스)를 만들거나 복사하려 하면 오류가 발생하며 컴파일러에서 결과적으로 컴파일러 오류 C2280을 발생합니다.  
  
    ```Output  
    error C2280: 'B::B(const B &)': attempting to reference a deleted function  
    ```  
  
     예제(이전)  
  
    ```cpp  
    struct A  
    {  
      volatile int i;  
      volatile int j;  
    };  
  
    extern A* pa;  
  
    struct B  
    {  
      union  
      {  
        A a;  
        int i;  
      };  
    };  
  
    B b1 {*pa};  
    B b2 (b1);  // error C2280  
    ```  
  
     예제(이후)  
  
    ```cpp  
    struct A  
    {  
      int i;int j;  
    };  
  
    extern volatile A* pa;  
  
    A getA()  // returns an A instance copied from contents of pa  
    {  
      A a;  
      a.i = pa->i;  
      a.j = pa->j;  
      return a;  
    }  
  
    struct B;  // as above  
  
    B b1 {GetA()};  
    B b2 (b1);  // error C2280  
    ```  
  
-   **정적 멤버 함수는 cv 한정자를 지원하지 않습니다.**  
  
     이전 버전의 Visual C++ 2015는 정적 멤버 함수에 cv 한정자가 포함되는 것을 허용했습니다. 이 동작은 Visual C++ 2015 및 Visual C++ 2015 업데이트 1에서의 문제 재발로 인한 것입니다. Visual C++ 2013 및 이전 버전의 Visual C++는 이런 식으로 작성된 코드를 거부합니다. Visual C++ 2015 및 Visual C++ 2015 업데이트 1의 동작은 잘못되었으며 C++ 표준과 일치하지 않습니다.  Visual Studio 2015 업데이트 2는 이런 식으로 작성된 코드를 거부하며 대신 컴파일러 오류 C2511을 발생합니다.  
  
    ```Output  
    error C2511: 'void A::func(void) const': overloaded member function not found in 'A'  
    ```  
  
     예제(이전)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() const {}  // C2511  
  
    ```  
  
     예제(이후)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() {}  // removed const  
  
    ```  
  
-   **열거형의 정방향 선언은 WinRT 코드에서 허용되지 않습니다**(/ZW만 영향을 줌).  
  
     WinRT(Windows 런타임)에 대해 컴파일된 코드는 `enum` 형식이 정방향 선언되는 것을 허용하지 않습니다. /clr 컴파일러 스위치를 사용하여 관리되는 C++ 코드가 .Net Framework에 대해 컴파일되는 경우와 비슷합니다. 이 동작은 열거형의 크기를 항상 알 수 있으며 WinRT 형식 시스템에 올바르게 프로젝션될 수 있음을 확인합니다. 컴파일러는 이러한 방식으로 작성된 코드를 거부하고 컴파일러 오류 C3197과 함께 컴파일러 오류 C2599를 발생합니다.  
  
    ```Output  
    error C2599: 'CustomEnum': the forward declaration of a WinRT enum is not allowed  
    ```  
  
    ```Output  
    error C3197: 'public': can only be used in definitions  
    ```  
  
     예제(이전)  
  
    ```cpp  
    namespace A {  
      public enum class CustomEnum: int32;  // forward declaration; error C2599, error C3197  
    }  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
     예제(이후)  
  
    ```cpp  
              // forward declaration of CustomEnum removed  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
-   **오버로드된 멤버가 아닌 연산자 new 및 연산자 delete는 인라인으로 선언할 수 없습니다**(수준 1(/ W1)이 기본적으로 설정되어 있음).  
  
     이전 버전의 컴파일러는 멤버가 아닌 연산자 new 및 연산자 delete 함수가 인라인으로 선언될 때 경고를 발생하지 않습니다. 이 방식으로 작성된 코드는 형식이 잘못되었으며(진단이 필요하지 않음) 진단하기 힘들 수 있는 일치하지 않는 new 및 delete 연산자로 인해 특히 크기가 지정된 할당 해제와 함께 사용 시 메모리 문제를 일으킬 수 있습니다.   이제 컴파일러는 이런 식으로 작성된 코드를 식별하기 위해 경고 C4595를 발생합니다.  
  
    ```Output  
    warning C4595: 'operator new': non-member operator new or delete functions may not be declared inline  
    ```  
  
     예제(이전)  
  
    ```cpp  
              inline void* operator new(size_t sz)  // warning C4595  
    {  
      ...  
    }  
    ```  
  
     예제(이후)  
  
    ```cpp  
              void* operator new(size_t sz)  // removed inline  
    {  
      ...  
    }  
    ```  
  
     이러한 방식으로 작성된 코드를 수정하려면 연산자 정의를 헤더 파일에서 해당하는 소스 파일로 이동해야 합니다.  
  
##  <a name="VS_Update3"></a> 업데이트 3의 규칙 향상  
  
-   **이제 std::is_convertable이 자체 할당을 검색함**(표준 라이브러리)  
  
     이전 버전의 `std::is_convertable` 형식 특성은 복사 생성자가 삭제되거나 private인 경우 클래스 형식의 자체 할당을 제대로 검색하지 못했습니다. 이제 복사 생성자가 삭제되거나 private인 클래스 형식에 적용할 때 `std::is_convertable<>::value`이 `false`로 올바르게 설정됩니다.  
  
     이 변경과 관련된 컴파일러 진단은 없습니다.  
  
     예제  
  
    ```cpp  
    #include <type_traits>  
  
    class X1  
    {  
    public:  
        X1(const X1&) = delete;  
    };  
  
    class X2  
    {  
    private:  
        X2(const X2&);  
    };  
  
    static_assert(std::is_convertible<X1&, X1>::value, "BOOM");static_assert(std::is_convertible<X2&, X2>::value, "BOOM");  
    ```  
  
     이전 버전의 Visual C++에서는 `std::is_convertable<>::value`가 `true`로 잘못 설정되었기 때문에 이 예제의 맨 아래에 있는 정적 어설션이 성공합니다. 이제 `std::is_convertable<>::value`이 `false`로 올바르게 설정되므로 정적 어설션이 실패합니다.  
  
-   **기본값으로 설정되었거나 삭제된 trivial 복사 및 이동 생성자가 액세스 지정자를 따름**  
  
     이전 버전의 컴파일러에서는 호출을 허용하기 전에 기본값으로 설정되었거나 삭제된 trivial 복사 및 이동 생성자의 액세스 지정자를 확인하지 않았습니다. 이 이전 동작은 올바르지 않으며 C++ 표준을 따르지 않습니다. 경우에 따라 이 이전 동작으로 잘못된 코드가 자동으로 생성되어 예기치 않은 런타임 동작이 발생하는 위험이 초래되었습니다. 이제 컴파일러에서 기본값으로 설정되었거나 삭제된 trivial 복사 및 이동 생성자의 액세스 지정자를 검사하여 호출 가능 여부를 확인하고, 호출할 수 없는 경우 결과로 컴파일러 경고 C2248을 실행합니다.  
  
    ```Output  
    error C2248: 'S::S' cannot access private member declared in class 'S'  
    ```  
  
     예제(이전)  
  
    ```cpp  
    class S {  
    public:  
           S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(S);  // pass S by value  
  
    int main()  
    {  
        S s;  
        f(s);  // error C2248, can't invoke private copy constructor  
    }  
    ```  
  
     예제(이후)  
  
    ```cpp  
    class S {  
    public:  
           S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(const S&);  // pass S by reference  
  
    int main()  
    {  
        S s;  
        f(s);  
    }  
    ```  
  
-   **특성 사용 ATL 코드 지원 중단**(기본적으로 수준 1(/W1) 설정)  
  
     이전 버전의 컴파일러에서는 특성 사용 ATL 코드를 지원했습니다. [Visual C++ 2008부터 시작](https://msdn.microsoft.com/library/bb384632\(v=vs.90\).aspx)된 특성 사용 ATL 코드 지원 제거의 다음 단계로 특성 사용 ATL 코드가 더 이상 사용되지 않습니다. 이제 컴파일러에서 사용되지 않는 이러한 종류의 코드를 식별하기 위해 컴파일러 경고 C4467을 실행합니다.  
  
    ```Output  
    warning C4467: Usage of ATL attributes is deprecated  
    ```  
  
     컴파일러에서 지원이 제거될 때까지 특성 사용 ATL 코드를 계속 사용하려는 경우 `/Wv:18` 또는 `/wd4467` 명령줄 인수를 컴파일러에 전달하거나 소스 코드에 `#pragma warning(disable:4467)`을 추가하여 이 경고를 해제할 수 있습니다.  
  
     예제 1(이전)  
  
    ```cpp  
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]  
    class A {};  
    ```  
  
     예제 1(이후)  
  
    ```cpp  
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};  
  
    ```  
  
     사용되지 않는 ATL 특성의 사용을 방지하기 위해 아래 예제 코드와 같이 IDL 파일을 만들 수 있습니다.  
  
     예제 2(이전)  
  
    ```cpp  
    [emitidl];  
    [module(name="Foo")];  
  
    [object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]  
    __interface ICustom {  
        HRESULT Custom([in] long l, [out, retval] long *pLong);  
        [local] HRESULT CustomLocal([in] long l, [out, retval] long *pLong);  
    };  
  
    [coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]  
    class CFoo : public ICustom  
    {  
        // ...  
    };  
    ```  
  
     먼저 *.idl 파일을 만듭니다. 생성된 vc140.idl 파일을 사용하여 인터페이스와 주석이 포함된 \*.idl 파일을 가져올 수 있습니다.  
  
     그런 다음 빌드에 MIDL 단계를 추가하여 C++ 인터페이스 정의가 생성되었는지 확인합니다.  
  
     예제 2 IDL(이후)  
  
    ```cpp  
    import "docobj.idl";  
  
    [  
        object,local,uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)  
    ]  
  
    interface ICustom : IUnknown {  
        HRESULT  Custom([in] long l, [out,retval] long *pLong);  
        [local] HRESULT  CustomLocal([in] long l, [out,retval] long *pLong);  
    };  
  
    [ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]  
    library Foo  
    {  
        importlib("stdole2.tlb");  
        importlib("olepro32.dll");  
            [  
                version(1.0),  
                appobject,uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)  
            ]  
  
        coclass CFoo {  
            interface ICustom;  
        };  
    }  
    ```  
  
     아래 예제 코드와 같이 구현 파일에서 직접 ATL을 사용합니다.  
  
     예제 2 구현(이후)  
  
    ```cpp  
    #include <idl.header.h>  
    #include <atlbase.h>  
  
    class ATL_NO_VTABLE CFooImpl :  
        public ICustom,  
        public ATL::CComObjectRootEx<CComMultiThreadModel>  
    {  
    public:  
        BEGIN_COM_MAP(CFooImpl)  
        COM_INTERFACE_ENTRY(ICustom)  
        END_COM_MAP()  
    };  
    ```  
  
-   **미리 컴파일된 헤더(PCH) 파일 및 일치하지 않는 #include 지시문**(/Wall /WX에만 적용)  
  
     이전 버전의 컴파일러에서는 미리 컴파일된 헤더(PCH) 파일을 사용할 때 `-Yc` 및 `-Yu` 컴파일 간에 일치하지 않는 소스 파일의 `#include` 지시문을 허용했습니다. 이런 방식으로 작성된 코드는 컴파일러에서 더 이상 허용되지 않습니다.   PCH 파일 사용 시 일치하지 않는 `#include` 지시문을 식별하기 위해 이제 컴파일러에서 컴파일러 경고 CC4598을 실행합니다.  
  
    ```Output  
    warning C4598: 'b.h': included header file specified for Ycc.h at position 2 does not match Yuc.h at that position  
    ```  
  
     예제(이전):  
  
     X.cpp(-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"  
    #include "c.h"  
    ```  
  
     Z.cpp(-Yuc.h)  
  
    ```cpp  
    #include "b.h"  
    #include "a.h"  // mismatched order relative to X.cpp  
    #include "c.h"  
    ```  
  
     예제(이후)  
  
     X.cpp(-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"   
    #include "c.h"  
    ```  
  
     Z.cpp(-Yuc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h" // matched order relative to X.cpp  
    #include "c.h"  
    ```  
  
-   **미리 컴파일된 헤더(PCH) 파일 및 일치하지 않는 include 지시문**(/Wall /WX에만 적용)  
  
     이전 버전의 컴파일러에서는 미리 컴파일된 헤더(PCH) 파일을 사용할 때 `-Yc` 및 `-Yu` 컴파일 간에 일치하지 않는 컴파일러의 include 디렉터리(`-I`) 명령줄 인수를 허용했습니다. 이런 방식으로 작성된 코드는 컴파일러에서 더 이상 허용되지 않습니다.   PCH 파일 사용 시 일치하지 않는 include 디렉터리(`-I`) 명령줄 인수를 식별하기 위해 이제 컴파일러에서 컴파일러 경고 CC4599를 실행합니다.  
  
    ```Output  
    warning C4599: '-I..' : specified for Ycc.h at position 1 does not match Yuc.h at that position  
    ```  
  
     예제(이전)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h Z.cpp  
    ```  
  
     예제(이후)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h -I.. Z.cpp  
    ```
