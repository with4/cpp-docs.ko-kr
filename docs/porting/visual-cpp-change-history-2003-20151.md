---
title: "Visual C++ 2015의 주요 변경 내용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "주요 변경 내용[C++]"
ms.assetid: b38385a9-a483-4de9-99a6-797488bc5110
caps.latest.revision: 124
caps.handback.revision: 117
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++ 2015의 주요 변경 내용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

새 버전의 Visual C\+\+ 컴파일러로 업그레이드하는 경우 이전에 컴파일하고 올바르게 실행된 코드에서 컴파일 및\/또는 런타임 오류가 발생할 수 있습니다. 그러한 문제가 발생하는 새 버전의 변경 사항은 *주요 변경 사항*이라고 하고 일반적으로 C\+\+ 언어 표준, 함수 서명 또는 메모리의 레이아웃 개체 수정에 필요합니다.  
  
 검색 및 진단하기 어려운 런타임 오류를 방지하려면 다양한 버전의 컴파일러를 사용하여 컴파일된 바이너리에 정적으로 연결하지 않는 것이 좋습니다. 또한 EXE 또는 DLL 프로젝트를 업그레이드하는 경우 연결되는 라이브러리를 업그레이드해야 합니다. CRT\(C 런타임\) 또는 STL\(표준 템플릿 라이브러리\) 형식을 사용하고 있는 경우 다양한 버전의 컴파일러를 사용하여 컴파일된 바이너리\(DLL 포함\) 간에 CRT 또는 STL을 전달하지 마세요. 자세한 내용은 [DLL 경계를 넘어 CRT 개체를 전달할 때 발생할 수 있는 오류](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)를 참조하세요.  
  
 또한 COM 인터페이스 또는 POD 개체가 아닌 개체에 대한 특정 레이아웃에 의존하는 코드는 작성하지 않는 것이 좋습니다. 그러한 코드를 작성하는 경우 업그레이드한 후 작동하는지 확인해야 합니다. 자세한 내용은 [ABI 경계의 이식성](../cpp/portability-at-abi-boundaries-modern-cpp.md)을 참조하세요.  
  
 이 문서의 나머지 부분에서는 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]의 특정 주요 변경 사항을 설명하고 이 문서에서 “새 동작" 또는 “현재"라는 용어는 해당 버전을 나타냅니다. "이전 동작" 및 "이전"은 Visual Studio 2013 이하 릴리스를 나타냅니다. Visual Studio 2015 업데이트 1의 추가 변경 내용에 대한 자세한 내용은 [업데이트 1의 주요 변경 내용](../misc/breaking-changes-in-visual-cpp-2015-update-1.md)을 참조하세요.  
  
1.  [컴파일러 주요 변경 내용](#BK_compiler)  
  
2.  [CRT\(C 런타임\) 라이브러리 주요 변경 내용](#BK_CRT)  
  
3.  [표준 C\+\+ 및 STL\(표준 템플릿 라이브러리\) 주요 변경 내용](#BK_STL)  
  
4.  [MFC 및 ATL 주요 변경 내용](#BK_MFC)  
  
5.  [동시성 런타임 주요 변경 내용](#BK_ConcRT)  
  
##  <a name="BK_compiler"></a> Visual C\+\+ 컴파일러  
  
-   \/Zc:forScope\- 옵션  
  
     **\/Zc:forScope\-** 컴파일러 옵션은 사용되지 않으므로 이후 릴리스에서 제거될 예정입니다.  
  
    ```  
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release  
    ```  
  
     옵션은 대개 표준에 따라 범위를 벗어나야 하는 지점 뒤에서 루프 변수를 사용하는 비표준 코드를 허용하려고 사용됩니다. \/Za를 사용하지 않으면 루프 끝에 for 루프 변수를 항상 사용할 수 있으므로 \/Za 옵션으로 컴파일할 경우에만 필요합니다. 표준 준수가 중요하지 않으면\(예: 코드가 다른 컴파일러에 이식 가능하지 않은 경우\) \/Za 옵션을 해제하거나 언어 확장 사용 안 함 속성을 아니요로 설정할 수 있습니다. 이식 가능한 표준 규격 코드를 작성해야 하면 변수의 선언을 루프 외부 지점으로 이동하여 표준을 따르도록 코드를 다시 작성해야 합니다.  
  
    ```  
    // zc_forScope.cpp // compile with: /Zc:forScope- /Za // C2065 expected int main() { // Uncomment the following line to resolve. // int i; for (int i =0; i < 1; i++) ; i = 20;   // i has already gone out of scope under /Za }  
    ```  
  
-   **\/Zg 컴파일러 옵션**  
  
     \/Zg 컴파일러 옵션\(함수 프로토타입 생성\)은 더 이상 사용할 수 없습니다. 이 컴파일러 옵션은 이미 사용되지 않습니다.  
  
-   mstest.exe를 사용하여 명령줄에서 C\+\+\/CLI에 대한 단위 테스트를 더 이상 실행할 수 없습니다. 대신에 vstest.console.exe를 사용하세요.[VSTest.Console.exe 명령줄 옵션](../Topic/VSTest.Console.exe%20command-line%20options.md)을 참조하세요.  
  
-   **mutable 키워드**  
  
     이전에 오류 없이 컴파일했던 위치에서 `mutable` 저장소 클래스 지정자가 더 이상 허용되지 않습니다. 현재 컴파일러에서는 오류 C2071\(저장소 클래스가 잘못되었습니다.\)을 표시합니다. 표준에 따라 mutable 지정자는 클래스 데이터 멤버의 이름에만 적용되고 const 또는 static으로 선언된 이름과 참조 멤버에는 적용할 수 없습니다.  
  
     예를 들어, 다음 코드를 고려하세요.  
  
    ```  
    struct S { mutable int &r; };  
    ```  
  
     이전 Visual C\+\+ 컴파일러 버전에서는 이를 허용했으나 현재 컴파일러에서는 다음 오류를 표시합니다.  
  
    ```Output  
    오류 C2071: 'S::r': 저장소 클래스가 잘못되었습니다.  
    ```  
  
     오류를 수정하려면 중복 mutable 키워드를 제거하세요.  
  
-   **char\_16\_t 및 char32\_t**  
  
     `char16_t` 또는 `char32_t` 형식은 현재 기본 제공으로 처리되므로 typedef에서 이들 형식을 별칭으로 더 이상 사용할 수 없습니다. 사용자와 라이브러리 작성자가 char16\_t 및 char32\_t를 각각 uint16\_t 및 uint32\_t의 별칭으로 정의하는 것이 일반적이었습니다.  
  
    ```  
    #include <cstdint> typedef uint16_t char16_t; //C2628 typedef uint32_t char32_t; //C2628 int main(int argc, char* argv[]) { uint16_t x = 1; uint32_t y = 2; char16_t a = x; char32_t b = y; return 0; }  
    ```  
  
     코드를 업데이트하려면 typedef 선언을 제거하고 이들 이름과 충돌하는 다른 식별자의 이름을 바꿉니다.  
  
-   **비형식 템플릿 매개 변수**  
  
     이제는 비형식 템플릿 매개 변수가 포함된 특정 코드에 명시적 템플릿 인수를 제공하면 형식 호환성 검사가 정확하게 수행됩니다. 예를 들어 다음 코드는 이전 Visual C\+\+ 버전에서는 오류 없이 컴파일되었습니다.  
  
    ```  
    struct S1 { void f(int); void f(int, int); }; struct S2 { template <class C, void (C::*Function)(int) const> void f() {} }; void f() { S2 s2; s2.f<S1, &S1::f>(); }  
  
    ```  
  
     템플릿 매개 변수 형식이 템플릿 인수와 일치하지 않기 때문에 현재 컴파일러에서 제대로 오류를 표시합니다. 매개 변수는 const 멤버의 포인터이나 f 함수는 비const입니다.  
  
    ```Output  
    오류 C2893: 'void S2::f(void)' 함수 템플릿을 특수화하지 못했습니다. 참고: 다음 템플릿 인수 사용: 참고: 'C=S1' 참고: 'Function=S1::f'  
    ```  
  
     코드에서 이 오류를 해결하려면 사용하는 템플릿 인수 형식이 템플릿 매개 변수의 선언된 형식과 일치해야 합니다.  
  
-   **\_\_declspec\(align\)**  
  
     컴파일러가 함수에서 `__declspec(align)`을 더 이상 허용하지 않습니다. 이는 항상 무시되었지만 현재는 컴파일러 오류가 생성됩니다.  
  
    ```  
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations  
    ```  
  
     이 문제를 수정하려면 함수 선언에서 `__declspec(align)`을 제거합니다. 아무런 영향이 없으므로 제거해도 아무것도 변경되지 않습니다.  
  
-   **예외 처리**  
  
     예외 처리에 대한 몇 가지 변경 내용이 있습니다. 먼저 예외 개체는 복사 가능하거나 이동 가능해야 합니다. 다음 코드는 [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서 컴파일되었지만 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서는 컴파일되지 않습니다.  
  
    ```  
    struct S { public: S(); private: S(const S &); }; int main() { throw S(); // error }  
  
    ```  
  
     문제는 복사 생성자가 private이라는 점이므로 일반적인 예외 처리 과정으로는 개체를 복사할 수 없습니다. 복사 생성자가 `explicit`로 선언될 경우에도 마찬가지입니다.  
  
    ```  
    struct S { S(); explicit S(const S &); }; int main() { throw S(); // error }  
  
    ```  
  
     코드를 업데이트하려면 예외 개체에 대한 복사 생성자가 public이고 `explicit`로 표시되지 않아야 합니다.  
  
     값으로 예외를 catch하려면 예외 개체가 복사 가능해야 합니다. 다음 코드는 [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서 컴파일되었지만 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서는 컴파일되지 않습니다.  
  
    ```  
    struct B { public: B(); private: B(const B &); }; struct D : public B { }; int main() { try { } catch (D d) // error { } }  
  
    ```  
  
     참조에 대한 `catch`의 매개 변수 형식을 변경하여 이 문제를 해결할 수 있습니다.  
  
    ```  
    catch(D& d) { }  
    ```  
  
-   **매크로 뒤의 문자열 리터럴**  
  
     현재 컴파일러는 사용자 정의 리터럴을 지원합니다. 따라서 중간 공백 없이 매크로 뒤의 문자열 리터럴은 오류나 예기치 않은 결과를 생성할 수 있는 사용자 정의 리터럴로 해석됩니다. 예를 들어 이전 컴파일러에서는 다음 코드가 성공적으로 컴파일되었습니다.  
  
    ```  
    #define _x "there" char* func() { return "hello"_x; } int main() { char * p = func(); return 0; }  
    ```  
  
     컴파일러에서 이 코드는 매크로 뒤의 문자열 리터럴 "hello"로 해석되고 “there”로 확장되었고 두 문자열 리터럴은 하나로 연결되었습니다.[!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서 컴파일러는 이 코드를 사용자 정의 리터럴로 해석하지만 일치하는 사용자 정의 리터럴 \_x가 정의되지 않았으므로 오류가 발생합니다.  
  
    ```  
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found note: Did you forget a space between the string literal and the prefix of the following string literal?  
  
    ```  
  
     이 문제를 수정하려면 문자열 리터럴과 매크로 사이에 공백을 추가합니다.  
  
-   **인접 문자열 리터럴**  
  
     이전과 비슷하게 문자열 구문 분석의 관련 변경 내용 때문에 공백이 없는 인접 문자열 리터럴\(전각 또는 반각 문자 문자열 리터럴\)은 이전 Visual C\+\+ 릴리스에서 하나의 연결된 문자열로 해석되었습니다.[!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서는 현재 두 문자열 사이에 공백을 추가해야 합니다. 예를 들어 다음 코드를 변경해야 합니다.  
  
    ```  
    char * str = "abc""def";  
    ```  
  
     두 문자열 사이에 공백을 추가하면 됩니다.  
  
    ```  
    char * str = "abc" "def";  
    ```  
  
-   **Placement new 및 delete**  
  
     delete 연산자는 C\+\+14 표준을 준수하도록 변경되었습니다. 표준 변경에 대한 자세한 내용은 [C\+\+ 크기 지정된 할당 해제](http://isocpp.org/files/papers/n3778.html)\(영문\)를 참조하세요. 변경을 통해 size 매개 변수를 사용하는 전역 delete 연산자의 형식이 추가됩니다. 주요 변경 내용에 따르면 이전에는 placement new 연산자와 일치하도록 같은 서명으로 delete 연산자를 사용하면 placement new가 사용된 지점에서 컴파일러 오류\(C2956\)가 발생했습니다. 이 지점은 컴파일러가 해당하는 일치 delete 연산자를 식별하려고 하는 코드의 위치이기 때문입니다.  
  
     `void operator delete(void *, size_t)` 함수는 C\+\+11의 placement new 함수 "void \* 연산자 new\(size\_t, size\_t\)"와 일치하는 placement delete 연산자였습니다. C\+\+14 크기 지정된 할당 해제를 사용하면 이 delete 함수는 현재 *usual deallocation 함수*\(전역 delete 연산자\)입니다. 표준에 따르면 placement new를 사용하여 해당하는 delete 함수를 조회하고 usual deallocation 함수를 찾으면 프로그램에 잘못된 형식이 사용됩니다.  
  
     예를 들어 코드에서 placement new 및 placement delete를 둘 다 정의한다고 가정합니다.  
  
    ```  
    void * operator new(std::size_t, std::size_t); void operator delete(void*, std::size_t) noexcept;  
  
    ```  
  
     정의한 placement delete 연산자와 새 전역 크기 지정된 delete 연산자 간에 함수 서명이 일치하기 때문에 문제가 발생합니다. placement new 및 delete 연산자에 대해 size\_t 이외의 다른 연산자를 사용할 수 있는지를 고려하세요.  size\_t typedef의 형식은 컴파일러에 따라 결정되고 Visual C\+\+에서는 부호 없는 int에 대한 typedef입니다. 이 문제를 해결하려면 다음과 같은 열거된 형식을 사용하는 것이 좋습니다.  
  
    ```  
    enum class my_type : size_t {};  
  
    ```  
  
     그다음에 size\_t 대신 이 형식을 두 번째 인수로 사용하도록 placement new 및 delete의 정의를 변경합니다. placement new에 대한 호출을 업데이트하여 새 형식을 전달하고\(예: `static_cast<my_type>`을 사용하여 정수 값에서 변환\) new 및 delete의 정의를 업데이트하여 다시 정수 형식으로 캐스팅해야 합니다. 여기에 열거형을 사용할 필요가 없고 size\_t 멤버가 있는 클래스 형식도 사용할 수 있습니다.  
  
     또 다른 솔루션은 placement new를 함께 제거하는 것입니다. 코드에서 placement new를 사용하여 placement 인수가 할당되거나 삭제되는 개체 크기와 같은 메모리 풀을 구현하면 사용자 지정 메모리 풀 코드를 바꾸는 데는 크기 지정된 할당 해제 기능이 적합할 수 있고, placement 함수를 제거하고 placement 대신에 인수가 두 개인 delete 연산자만 사용할 수 있습니다.  
  
     코드를 바로 업데이트하지 않으려면 컴파일러 옵션 \/Zc:sizedDealloc\-를 사용하여 이전 동작으로 되돌릴 수 있습니다. 이 옵션을 사용하면 인수가 두 개인 delete 함수가 존재하지 않으므로 placement delete 연산자와 충돌하지 않습니다.  
  
-   **공용 구조체 데이터 멤버**  
  
     공용 구조체의 데이터 멤버는 더 이상 참조 형식을 포함할 수 없습니다.[!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서는 다음 코드가 성공적으로 컴파일되었지만 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서는 오류가 발생합니다.  
  
    ```  
    union U1 { const int i; }; union U2 { int &i; }; union U3 { struct {int &i;}; };  
    ```  
  
     앞의 코드에서 발생하는 오류는 다음과 같습니다.  
  
    ```Output  
    test.cpp(67): 오류 C2625: 'U2::i': 잘못된 공용 구조체 멤버입니다. 'int &' 형식은 참조 형식입니다. test.cpp(70): 오류 C2625: 'U3::i': 잘못된 공용 구조체 멤버입니다. 'int &' 형식은 참조 형식입니다.  
    ```  
  
     이 문제를 해결하려면 참조 형식을 포인터 또는 값으로 변경합니다. 형식을 포인터로 변경하려면 공용 구조체 필드를 사용하는 코드를 변경해야 합니다. 코드를 값으로 변경하면 공용 구조체에 저장된 데이터가 변경되며, union 형식의 필드는 같은 메모리를 공유하므로 이 변경이 다른 필드에 영향을 미칩니다. 값 크기에 따라 공용 구조체 크기도 변경할 수 있습니다.  
  
-   현재 익명 공용 구조체는 표준을 더 준수합니다. 이전 컴파일러 버전에서는 익명 공용 구조체에 대한 명시적 생성자 및 소멸자를 생성했습니다. 이 기능은 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서 삭제되었습니다.  
  
    ```  
    struct S { S(); }; union { struct { S s; }; } u; // C2280  
    ```  
  
     앞의 코드는 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서 다음 오류를 생성합니다.  
  
    ```  
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here  
    ```  
  
     이 문제를 해결하려면 생성자 및\/또는 소멸자의 정의를 제공하세요.  
  
    ```  
    struct S { // Provide a default constructor by adding an empty function body. S() {} }; union { struct { S s; }; } u;  
    ```  
  
-   **익명 구조체가 있는 공용 구조체**  
  
     공용 구조체에서 익명 구조체 멤버의 런타임 동작이 표준을 준수하도록 변경되었습니다. 해당 공용 구조체가 생성될 때 공용 구조체의 익명 구조체 멤버에 대한 생성자가 더 이상 암시적으로 호출되지 않습니다. 또한 공용 구조체가 범위를 벗어날 때 공용 구조체의 익명 구조체 멤버에 대한 소멸자가 더 이상 암시적으로 호출되지 않습니다. 소멸자가 있는 명명된 구조체 S 멤버가 포함된 익명 구조체가 공용 구조체 U에 들어 있는 다음 코드를 고려하세요.  
  
    ```  
    #include <stdio.h> struct S { S() { printf("Creating S\n"); } ~S(){ printf("Destroying S\n"); } }; union U { struct { S s; }; U() {} ~U(){} }; void f() { U u; // Destructor implicitly called here. } int main() { f(); char s[1024]; printf("Press any key.\n"); gets_s(s); return 0; }  
    ```  
  
     [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서 S에 대한 생성자는 공용 구조체가 생성될 때 호출되고 S에 대한 소멸자는 f 함수의 스택이 정리될 때 호출됩니다. 그러나 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서는 생성자와 소멸자가 호출되지 않습니다. 컴파일러에서 이 동작 변경에 대해 경고를 표시합니다.  
  
    ```Output  
    경고 C4587: 'U::s': 동작 변경: 생성자가 더 이상 암시적으로 호출되지 않습니다. 경고 C4588: 'U::s': 동작 변경: 소멸자가 더 이상 암시적으로 호출되지 않습니다.  
    ```  
  
     원래 동작을 복원하려면 익명 구조체에 이름을 지정합니다. 익명이 아닌 구조체의 런타임 동작은 컴파일러 버전과 관계없이 동일합니다.  
  
    ```  
    #include <stdio.h> struct S { S() { printf("Creating S.\n"); } ~S() { printf("Destroying S\n"); } }; union U { struct { S s; } namedStruct; U() {} ~U() {} }; void f() { U u; } int main() { f(); char s[1024]; printf("Press any key.\n"); gets_s(s); return 0; }  
    ```  
  
     또는 생성자 및 소멸자 코드를 새 함수로 이동하고 공용 구조체에 대한 생성자 및 소멸자에서 이들 함수에 호출을 추가하세요.  
  
    ```  
    #include <stdio.h> struct S { void Create() { printf("Creating S.\n"); } void Destroy() { printf("Destroying S\n"); } }; union U { struct { S s; }; U() { s.Create();  } ~U() { s.Destroy(); } }; void f() { U u; } int main() { f(); char s[1024]; printf("Press any key.\n"); gets_s(s); return 0; }  
    ```  
  
-   **템플릿 확인**  
  
     템플릿의 이름 확인에 대한 변경 내용이 있습니다. C\+\+에서 이름을 확인할 후보를 고려할 때 잠재적인 일치 항목으로 고려 중인 하나 이상의 이름에서 잘못된 템플릿 인스턴스화가 생성될 수 있습니다. 보통 이들 잘못된 인스턴스화 때문에 컴파일러 오류가 발생하지는 않습니다. 이 원칙을 SFINAE\(Substitution Failure Is Not An Error\)라고 합니다.  
  
     현재 SFINAE에 따라 컴파일러가 클래스 템플릿의 특수화를 인스턴스화해야 하면 이 프로세스 중에 발생하는 오류는 컴파일러 오류입니다. 이전 버전에서는 컴파일러가 해당 오류를 무시합니다. 예를 들어, 다음 코드를 고려하세요.  
  
    ```  
    #include <type_traits> template<typename T> struct S { S() = default; S(const S&); S(S&&); template<typename U, typename = typename std::enable_if<std::is_base_of<T, U>::value>::type> S(S<U>&&); }; struct D; void f1() { S<D> s1; S<D> s2(s1); } struct B { }; struct D : public B { }; void f2() { S<D> s1; S<D> s2(s1); }  
  
    ```  
  
     현재 컴파일러로 컴파일할 경우 다음 오류가 발생합니다.  
  
    ```Output  
    type_traits(1110): 오류 C2139: 'D': 정의되지 않은 클래스는 컴파일러 내장 형식 특성 '__is_base_of'에 대한 인수로 사용할 수 없습니다. \t331.cpp(14): 참고: 'D'에 대한 선언을 참조하세요. \t331.cpp(10): 참고: [ T=D, U=D ]로 컴파일 중인 클래스 템플릿 인스턴스화 'std::is_base_of<T,U>'에 대한 참조를 확인하세요.  
    ```  
  
     이는 is\_base\_of의 첫 번째 호출 지점에서 'D' 클래스가 아직 정의되지 않았기 때문입니다.  
  
     이 경우 문제를 해결하려면 클래스가 정의될 때까지 이러한 형식 특성을 사용하지 마세요. B 및 D의 정의를 코드 파일의 시작 부분으로 이동하면 오류가 해결됩니다. 정의가 헤더 파일에 있으면 헤더 파일의 include 문 순서를 확인하여 문제가 있는 템플릿이 사용되기 전에 클래스 정의가 컴파일되는지 확인합니다.  
  
-   **복사 생성자**  
  
     [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] 및 [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)]에서 컴파일러는 클래스에 사용자 정의 이동 생성자가 있지만 사용자 정의 복사 생성자가 없을 경우 해당 클래스에 대한 복사 생성자를 생성합니다. Dev14에서는 생성된 복사 생성자가 "\= delete"로 표시됩니다.  
  
##  <a name="BK_CRT"></a> CRT\(C 런타임 라이브러리\)  
  
### 일반 변경 내용  
  
-   **리팩터링된 이진 파일**  
  
     CRT 라이브러리가 다음 이진 파일 두 개로 리팩터링되었습니다. 범용 CRT\(ucrtbase\)에는 대부분 표준 기능이 포함되고 VC 런타임 라이브러리\(vcruntime140\)에는 컴파일러 관련 기능이 포함됩니다\(예: 예외 처리 및 내장\). 링커는 자동으로 새 기본 라이브러리를 사용하므로 기본 프로젝트 설정을 사용하면 이 변경이 영향을 미치지 않습니다. 프로젝트의 **링커** 속성 **모든 기본 라이브러리 무시**를 **예**로 설정했거나 명령줄에서 \/NODEFAULTLIB 링커 옵션을 사용 중이면 **추가 종속성** 속성에서 라이브러리 목록을 업데이트하여 새 리팩터링된 라이브러리를 포함해야 합니다. 이전 CRT 라이브러리\(libcmt.lib, libcmtd.lib, msvcrt.lib, msvcrtd.lib\)를 해당하는 리팩터링된 라이브러리로 바꿉니다. 두 리팩터링된 라이브러리에는 각각 정적\(.lib\) 및 동적\(.dll\) 버전과 릴리스\(접미사 없음\) 및 디버그\("d" 접미사 사용\) 버전이 있습니다. 동적 버전에는 연결할 가져오기 라이브러리가 포함됩니다. 두 리팩터링된 라이브러리에는 범용 CRT인, 특히 ucrtbase.dll 또는 .lib, ucrtbased.dll 또는 .lib와 VC 런타임 라이브러리인 libvcruntime.lib, libvcruntime.dll, libvcruntimed.lib 및 libvcruntimed.dll이 있습니다.[CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)을 참조하세요.  
  
### \<locale.h\>  
  
-   **localeconv**  
  
     locale.h에 선언된 [localeconv](../c-runtime-library/reference/localeconv.md) 함수는 현재 [per\-thread locale](../parallel/multithreading-and-locales.md)이 사용될 때 제대로 작동합니다. 이전 라이브러리 버전에서 이 함수는 스레드 로캘이 아니라 전역 로캘에 대해 lconv 데이터를 반환합니다.  
  
     스레드 단위 로캘을 사용할 경우 localeconv 사용을 확인하여 코드에서 반환된 lconv 데이터가 전역 로캘과 관련된다고 가정하는지 확인하고 적절히 수정해야 합니다.  
  
### \<math.h\>  
  
-   **수식 라이브러리 함수의 C\+\+ 오버로드**  
  
     이전 버전에서 \<math.h\>는 수식 라이브러리 함수에 대한 일부 C\+\+ 오버로드를 정의했습니다. \<cmath\>는 나머지 오버로드를 정의하므로 모든 오버로드를 가져오려면 \<cmath\> 헤더를 포함해야 했습니다. 이로 인해 \<math.h\>만 포함된 코드에서는 함수 오버로드 확인에 대한 문제가 발생했습니다. 현재 모든 C\+\+ 오버로드는 \<math.h\>에서 제거되었고 \<cmath\>에만 있습니다.  
  
     오류를 해결하려면 \<cmath\>를 포함하여 \<math.h\>에서 제거된 함수 선언을 가져옵니다. 다음 표에서는 이동된 함수를 보여 줍니다.  
  
     이동된 함수:  
  
    1.  double abs\(double\) 및 float abs\(float\)  
  
    2.  double pow\(double, int\), float pow\(float, float\), float pow\(float, int\), long double pow\(long double, long double\), long double pow\(long double, int\)  
  
    3.  부동 소수점 함수 acos, acosh, asin, asinh, atan, atanh, atan2, cbrt, ceil, copysign, cos, cosh, erf, erfc, exp, exp2, expm1, fabs, fdim, floor, fma, fmax, fmin, fmod, frexp, hypot, ilogb, ldexp, lgamma, llrint, llround, log, log10, log1p, log2, lrint, lround, modf, nearbyint, nextafter, nexttoward, remainder, remquo, rint, round, scalbln, scalbn, sin, sinh, sqrt, tan, tanh, tgamma, trunc의 float 및 long double 버전  
  
     math.h 헤더만 포함된 abs를 부동 소수점 형식과 함께 사용하는 코드가 있으면 부동 소수점 버전을 더 이상 사용할 수 없으므로 현재 호출은 부동 소수점 인수가 포함되더라도 abs\(int\)로 확인됩니다. 이로 인해 오류가 발생합니다.  
  
    ```Output  
    warning C4244: 'argument' : 'float'를 'int'로 변환하면서 데이터가 손실될 수 있습니다.  
    ```  
  
     이 경고를 해결하려면 abs에 대한 호출을 abs의 부동 소수점 버전\(예: double 인수에 대한 fabs 또는 float 인수에 대한 fabsf\)으로 바꾸거나, cmath 헤더를 포함하고 abs를 계속 사용합니다.  
  
-   **부동 소수점 적합성**  
  
     NaN 및 무한대와 같은 특수한 경우 입력과 관련된 IEEE\-754 및 C11 Annex F 사양에 대한 적합성을 향상하고자 수식 라이브러리가 많이 변경되었습니다. 예를 들어 이전 라이브러리 버전에서 종종 오류로 처리되었던 자동 NaN 입력은 더 이상 오류로 처리되지 않습니다.[IEEE 754 표준](http://grouper.ieee.org/groups/754)\(영문\) 및 [C11 표준](http://www.iso-9899.info/wiki/The_Standard)\(영문\)의 부록 F를 참조하세요.  
  
     이 변경 내용 때문에 컴파일 시간 오류가 발생하지 않지만, 프로그램이 표준에 따라 다르고 더 올바르게 동작할 수 있습니다.  
  
-   **FLT\_ROUNDS**  
  
     Visual Studio 2013에서 FLT\_ROUNDS 매크로는 상수 식으로 확장되었고, 이는 반올림 모드가 런타임에 fesetround 호출 등을 통해 구성 가능하기 때문에 올바르지 않았습니다. 현재 FLT\_ROUNDS 매크로는 동적이고 현재 반올림 모드를 올바르게 반영합니다.  
  
### \<new\> 및 \<new.h\>  
  
-   **new 및 delete**  
  
     이전 라이브러리 버전에서는 구현 시 정의된 연산자 new 및 delete 함수를 런타임 라이브러리 DLL\(예: msvcr120.dll\)에서 내보냈습니다. 현재 이들 연산자 함수는 런타임 라이브러리 DLL을 사용할 때라도 항상 정적으로 이진 파일에 연결됩니다.  
  
     이는 네이티브 또는 혼합 코드\(\/clr\)에 대한 주요 변경 내용이 아니지만 [\/clr:pure](../build/reference/clr-common-language-runtime-compilation.md)로 컴파일된 코드의 경우 이로 인해 코드가 컴파일되지 않을 수 있습니다. 코드를 \/clr:pure로 컴파일할 경우 이 변경으로 인한 빌드 오류를 해결하려면 \#include \<new\> 또는 \#include \<new.h\>를 추가해야 할 수 있습니다. \/clr:pure는 [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)]에서 사용되지 않으므로 이후 릴리스에서 제거될 예정입니다.  
  
### \<process.h\>  
  
-   **\_beginthread 및 \_beginthreadex**  
  
     [\_beginthread](../c-runtime-library/reference/beginthread-beginthreadex.md) 및 [\_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) 함수는 현재 스레드 기간에 대한 스레드 프로시저가 정의되어 있는 모듈에 대한 참조를 포함합니다. 이를 통해 스레드 실행이 완료될 때까지 모듈이 언로드되지 않도록 보장할 수 있습니다.  
  
### \<stdarg.h\>  
  
-   **va\_start 및 참조 형식**  
  
     C\+\+ 코드를 컴파일할 때 현재 [va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)는 컴파일 시간에 전달된 인수가 참조 형식이 아닌지 검사합니다. 참조 형식 인수는 C\+\+ 표준에 따라 금지됩니다.  
  
### \<stdio.h\> 및 \<conio.h\>  
  
-   **printf 및 scanf 함수 패밀리는 현재 인라인으로 정의됩니다.**  
  
     모든 printf 및 scanf 함수의 정의는 \<stdio.h\>, \<conio.h\> 및 기타 CRT 헤더로 인라인으로 이동되었습니다. 이 주요 변경 내용으로 인해 해당하는 CRT 헤더를 포함하지 않고 이들 함수를 로컬로 선언한 프로그램에 대한 링커 오류\(LNK2019, 확인되지 않은 외부 기호\)가 발생합니다. 가능하면 코드를 업데이트하여 인라인 함수 및 CRT 헤더를 포함\(\#include \<stdio.h\> 추가\)해야 하지만, 이들 헤더 파일을 포함하도록 코드를 수정하지 않으려면 대체 솔루션으로 링커 입력 legacy\_stdio\_definitions.lib에 추가 라이브러리를 추가합니다.  
  
     이 라이브러리를 IDE의 링커 입력에 추가하려면 프로젝트 노드의 상황에 맞는 메뉴를 열고, **속성**을 선택하고, **프로젝트 속성** 대화 상자에서 **링커**를 선택하고, **링커 입력**을 편집하여 legacy\_stdio\_definitions.lib를 세미콜론으로 구분된 목록에 추가합니다.  
  
     프로젝트가 Visual C\+\+ 2015 이전의 릴리스로 컴파일된 정적 라이브러리와 연결되면 링커에서 확인되지 않은 외부 기호가 보고될 수 있습니다. 이들 오류는 \_iob, \_iob\_func에 대한 내부 stdio 정의 또는 \_imp\_\* 형식의 특정 stdio 함수에 대한 관련 가져오기를 참조할 수 있습니다. 프로젝트를 업그레이드할 때 Visual C\+\+ 컴파일러 및 라이브러리의 최신 버전으로 모든 정적 라이브러리를 다시 컴파일하는 것이 좋습니다. 라이브러리가 소스를 사용할 수 없는 타사 라이브러리이면 타사로부터 업데이트된 라이브러리를 요청하거나 Visual C\+\+ 컴파일러 및 라이브러리의 이전 버전으로 컴파일하는 별도의 DLL로 해당 라이브러리 사용을 캡슐화해야 합니다.  
  
    > [!WARNING]
    >  Windows SDK 8.1 이하와 연결되어 있으면 이러한 확인되지 않은 외부 기호 오류가 발생할 수 있습니다. 이 경우 앞에 설명된 대로 링커 입력에 legacy\_stdio\_definitions.lib를 추가하여 오류를 해결해야 합니다.  
  
     확인되지 않은 기호 오류를 해결하려면 [dumpbin.exe](../build/reference/dumpbin-reference.md)를 사용하여 이진 파일에 정의된 기호를 검사해 볼 수 있습니다. 다음 명령줄을 실행하여 라이브러리에 정의된 기호를 확인해 보세요.  
  
    ```  
    dumpbin.exe /LINKERMEMBER somelibrary.lib  
    ```  
  
-   **gets 및 \_getws**  
  
     [gets](../c-runtime-library/gets-getws.md) 및 [\_getws](../c-runtime-library/gets-getws.md) 함수가 제거되었습니다. gets 함수는 안전하게 사용할 수 없으므로 C11의 C 표준 라이브러리에서 제거되었습니다. \_getws 함수는 gets와 동일한 Microsoft 확장이지만 전각 문자열에 해당했습니다. 이들 함수 대신 [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [gets\_s](../c-runtime-library/reference/gets-s-getws-s.md) 및 [\_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md)를 사용하는 것이 좋습니다.  
  
-   **\_cgets 및 \_cgetws**  
  
     [\_cgets](../c-runtime-library/cgets-cgetws.md) 및 [\_cgetws](../c-runtime-library/cgets-cgetws.md) 함수가 제거되었습니다. 이들 함수 대신 [\_cgets\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md) 및 [\_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)를 사용하는 것이 좋습니다.  
  
-   **무한대 및 NaN 서식 지정**  
  
     이전 버전에서 무한대 및 NaN은 일련의 Visual C\+\+ 관련 센티널 문자열을 사용하여 서식이 지정됩니다.  
  
    -   무한대: 1.\#INF  
  
    -   자동 NaN: 1.\#QNAN  
  
    -   신호 NaN: 1.\#SNAN  
  
    -   무한 NaN: 1.\#IND  
  
     이들 문자열 앞에 부호가 추가될 수 있고 필드 너비 및 정밀도에 따라 서식이 약간 다르게 지정되었을 수 있습니다. \#INF는 2자리 정밀도로 "반올림"되므로 경우에 따라 비정상적인 효과로 인해 printf\("%.2f\\n", INFINITY\)가 1.\#J를 인쇄할 수 있습니다. C99는 무한대 및 NaN 서식을 지정하는 방법에 대한 새로운 요구 사항을 새로 추가했습니다. Visual C\+\+ 구현은 현재 이들 요구 사항을 준수합니다. 새 문자열은 다음과 같습니다.  
  
    -   무한대: inf  
  
    -   자동 NaN: nan  
  
    -   신호 NaN: nan\(snan\)  
  
    -   무한 NaN: nan\(ind\)  
  
     이들 문자열 앞에 부호가 추가될 수 있습니다. 대문자 서식 지정자가 사용되면\(%f 대신 %F\) 문자열은 요구된 대로 대문자로 인쇄됩니다\(inf 대신 INF\).  
  
     [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) 함수는 이들 새 문자열을 구문 분석하도록 수정되었으므로 이들 문자열은 printf 및 scanf를 통해 왕복됩니다.  
  
-   **부동 소수점 서식 지정 및 구문 분석**  
  
     정확성을 향상하고자 새로운 부동 소수점 서식 지정 및 구문 분석 알고리즘이 새로 추가되었습니다. 이 변경은 함수의 [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 및 [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) 패밀리 및 [strtod](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md) 같은 함수에 영향을 미칩니다.  
  
     이전 서식 지정 알고리즘에서는 제한된 자릿수만 생성되고 나머지 소수 자릿수는 0으로 채워집니다. 일반적으로 다시 원래 부동 소수점 값으로 왕복할 문자열을 생성하려면 이것으로 충분하지만 정확한 값이나 가장 가까운 10진수 표현이 필요한 경우에는 적절하지 않습니다. 새 서식 지정 알고리즘에서는 값을 표현하는 데 필요한 만큼 자릿수가 생성되거나 지정된 정밀도가 채워집니다. 향상의 예로 2의 거듭제곱을 인쇄할 때 결과를 살펴보세요.  
  
    ```  
    printf("%.0f\n", pow(2.0, 80))  
  
    ```  
  
    ```Output  
        이전:  1208925819614629200000000    신규:  1208925819614629174706176  
    ```  
  
     이전 구문 분석 알고리즘에서는 입력 문자열에서 최대 17자리만 고려되고 나머지 자릿수는 무시됩니다. 문자열로 표현되는 값의 매우 가까운 근사치를 생성하려면 이것으로 충분하고 결과는 대개 올바르게 반올림됨 결과에 매우 가깝습니다. 새 구현에서는 모든 제공된 자릿수를 고려하고 모든 입력에 대한 올바르게 반올림된 결과를 생성합니다\(최대 768자리 길이\). 또한 현재 이들 함수는 반올림 모드를 따릅니다\(fesetround를 통해 제어 가능\).  이들 함수가 다른 결과를 출력할 수 있으므로 이는 잠재적으로 중요한 동작 변경입니다. 새 결과는 항상 이전 결과보다 더 정확합니다.  
  
-   **16진수 및 무한대\/NaN 부동 소수점 구문 분석**  
  
     부동 소수점 구문 분석 알고리즘은 현재 16진수 부동 소수점 문자열\(예: %a 및 %A printf 서식 지정자에서 생성된 항목\) 및 위 설명대로 printf 함수에서 생성된 모든 무한대 및 NaN 문자열을 구문 분석합니다.  
  
-   **%A 및 %a 영\(0\) 채우기**  
  
     %a 및 %A 서식 지정자는 부동 소수점 수의 서식을 16진수 가수 및 이진 지수로 지정합니다. 이전 버전에서 printf 함수는 문자열을 영\(0\)으로 올바르게 채우지 않습니다. 예를 들어 printf\("%07.0a\\n", 1.0\)은 0x01p\+0을 인쇄해야 하는데 00x1p\+0을 인쇄합니다. 이 문제는 수정되었습니다.  
  
-   **%A 및 %a 정밀도**  
  
     이전 라이브러리 버전에서 %A 및 %a 서식 지정자의 기본 정밀도는 6이었습니다. 현재 기본 정밀도는 C 표준에 따라 13입니다.  
  
     이는 %A 또는 %a와 함께 서식 문자열을 사용하는 함수 출력의 런타임 동작 변경입니다. 이전 동작에서 %A 지정자를 사용하는 출력은 "1.1A2B3Cp\+111"일 수 있습니다. 현재 같은 값의 출력은 "1.1A2B3C4D5E6F7p\+111"입니다. 이전 동작을 가져오려면 정밀도\(예: %.6A\)를 지정하면 됩니다.[전체 자릿수 사양](../c-runtime-library/precision-specification.md)을 참조하세요.  
  
-   **%F 지정자**  
  
     현재 %F 서식\/변환 지정자가 지원됩니다. 이는 무한대 및 NaN이 대문자로 서식 지정된다는 점을 제외하고 %f 서식 지정자와 일치하는 기능입니다.  
  
     이전 버전에서는 F 및 N을 길이 수정자로 구문 분석하는 데 구현이 사용되었습니다. 이 동작은 분할된 주소 공간의 보존 기간부터 계속 존재했습니다. 이들 길이 수정자는 %Fp 또는 %Ns에서와 같이 각각 먼 포인터와 가까운 포인터를 나타내는 데 사용되었습니다. 이 동작이 제거되었습니다. %F가 나타나면 현재 이는 %F 서식 지정자로 처리되고, %N이 나타나면 현재 이는 잘못된 매개 변수로 처리됩니다.  
  
-   **지수 서식 지정**  
  
     %e 및 %E 서식 지정자는 부동 소수점 수의 서식을 10진수 가수 및 지수로 지정합니다. 경우에 따라 %g 및 %G 서식 지정자는 숫자 서식을 이 형식으로 지정합니다. 이전 버전에서 CRT는 항상 3자리 지수가 포함된 문자열을 생성합니다. 예를 들어 printf\("%e\\n", 1.0\)는 1.000000e\+000을 인쇄합니다. 이 결과는 올바르지 않습니다. C에서는 지수가 1자리 또는 2자리로만 표현 가능할 경우 2자리만 인쇄되어야 합니다.  
  
     Visual Studio 2005에서 전역 규칙 스위치 [\_set\_output\_format](../c-runtime-library/set-output-format.md)이 추가되었습니다. 프로그램은 \_TWO\_DIGIT\_EXPONENT 인수와 함께 이 함수를 호출하여 규칙 지수 인쇄가 가능하도록 설정합니다. 기본 동작이 표준 준수 지수 인쇄 모드로 변경되었습니다.  
  
-   **서식 문자열 유효성 검사**  
  
     이전 버전에서 printf 및 scanf 함수는 경우에 따라 비정상적인 효과를 가진 잘못된 서식 문자열을 대부분 자동으로 수락합니다. 예를 들어 %hlhlhld가 %d로 처리됩니다. 현재 모든 잘못된 서식 문자열은 잘못된 매개 변수로 처리됩니다.  
  
-   **fopen 모드 문자열 유효성 검사**  
  
     이전 버전에서 fopen 함수 패밀리는 몇몇 잘못된 모드 문자열\(예: r\+b\+\)을 자동으로 수락했습니다. 현재는 잘못된 모드 문자열을 인식하여 잘못된 매개 변수로 처리됩니다.  
  
-   **\_O\_U8TEXT 모드**  
  
     현재 [\_setmode](../c-runtime-library/reference/setmode.md) 함수는 \_O\_U8TEXT 모드에서 열린 스트림의 모드를 올바르게 보고합니다. 이전 라이브러리 버전에서는 해당 스트림을 \_O\_WTEXT에서 열린 것으로 보고했습니다.  
  
     이는 코드가 인코딩이 UTF\-8인 스트림에 대한 \_O\_WTEXT 모드를 해석할 경우 주요 변경 내용입니다. 응용 프로그램이 UTF\_8을 지원하지 않으면 점점 더 일반화되는 이 인코딩에 대한 지원을 추가하는 것이 좋습니다.  
  
-   **snprintf 및 vsnprintf**  
  
     현재 [snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) 및 [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) 함수가 구현됩니다. 이전 코드에서는 이들 함수의 매크로 버전이 CRT 라이브러리에서 구현되지 않았기 때문에 매크로 버전을 정의에 제공했지만 새 버전에서는 더 이상 필요하지 않습니다. 현재 \<stdio.h\>를 포함하기 전에 [snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) 또는 [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)가 매크로로 정의되면 컴파일이 실패하고 매크로가 정의된 위치를 나타내는 오류가 발생합니다.  
  
     일반적으로 이 문제를 해결하려면 사용자 코드에서 snprintf 또는 vsnprintf의 선언을 삭제합니다.  
  
-   **tmpnam이 사용 가능한 파일 이름을 생성함**  
  
     이전 버전에서 tmpnam 및 tmpnam\_s 함수는 드라이브 루트\(예: \\sd3c.\)에 파일 이름을 생성했습니다. 현재 이들 함수는 임시 디렉터리에 사용 가능한 파일 이름 경로를 생성합니다.  
  
-   **FILE 캡슐화**  
  
     이전 버전에서 FILE 형식은 \<stdio.h\>에서 완전히 정의되었으므로 사용자 코드가 FILE에 도달하고 internal을 수정할 수 있었습니다. stdio 라이브러리가 구현 세부 정보를 숨기도록 변경되었습니다. 이와 함께 \<stdio.h\>에 정의된 FILE은 현재 불투명 형식이고 해당 멤버는 CRT 외부에서 액세스할 수 없습니다.  
  
-   **\_outp 및 \_inp**  
  
     [\_outp](../c-runtime-library/outp-outpw-outpd.md), [\_outpw](../c-runtime-library/outp-outpw-outpd.md), [\_outpd](../c-runtime-library/outp-outpw-outpd.md), [\_inp](../c-runtime-library/inp-inpw-inpd.md), [\_inpw](../c-runtime-library/inp-inpw-inpd.md) 및 [\_inpd](../c-runtime-library/inp-inpw-inpd.md) 함수가 제거되었습니다.  
  
### \<stdlib.h\>, \<malloc.h\> 및 \<sys\/stat.h\>  
  
-   **strtof 및 wcstof**  
  
     strtof 및 wcstof 함수의 경우 값이 float로 표현되지 않으면 errno를 ERANGE로 설정할 수가 없었습니다. 이 문제는 수정되었습니다. 이 오류는 이들 두 함수에만 발생했고 strtod, wcstod, strtold 및 wcstold 함수는 영향을 받지 않았습니다. 이는 런타임 관련 주요 변경 내용입니다.  
  
-   **맞춤 할당 함수**  
  
     이전 버전에서 맞춤 할당 함수\(\_aligned\_malloc, \_aligned\_offset\_malloc, etc.\)는 맞춤이 0인 블록에 대한 요청을 자동으로 수락했습니다. 요청된 맞춤은 0이 아닌 2의 거듭제곱이어야 합니다. 이 문제는 해결되었고 요청된 맞춤 0은 현재 잘못된 매개 변수로 처리됩니다. 이는 런타임 관련 주요 변경 내용입니다.  
  
-   **힙 함수**  
  
     \_heapadd, \_heapset 및 \_heapused 함수가 제거되었습니다. Windows 힙을 사용하도록 CRT가 업데이트된 후에는 이들 함수가 작동하지 않았습니다.  
  
-   **smallheap**  
  
     smalheap 링크 옵션이 제거되었습니다.[링크 옵션](../c-runtime-library/link-options.md)을 참조하세요.  
  
### \<string.h\>  
  
-   **wcstok**  
  
     wcstok 함수의 서명이 C 표준에 필요한 서명과 일치하도록 변경되었습니다. 이전 라이브러리 버전에서 이 함수의 서명은 다음과 같았습니다.  
  
    ```  
    wchar_t* wcstok(wchar_t*, wchar_t const*)  
    ```  
  
     내부 스레드 단위 컨텍스트를 사용하여 strtok의 경우와 마찬가지로 호출 전체에서 상태를 추적했습니다. 현재 이 함수는 서명 wchar\_t\* wcstok\(wchar\_t\*, wchar\_t const\*, wchar\_t\*\*\)를 포함하고 호출자가 컨텍스트를 세 번째 인수로 함수에 전달하도록 요구합니다.  
  
     쉽게 이식하도록 이전 서명과 함께 새 \_wcstok 함수가 추가되었습니다. C\+\+ 코드를 컴파일할 때 이전 서명이 포함된 wcstok의 인라인 오버로드도 있습니다. 이 오버로드는 deprecated로 선언되었습니다. C 코드에서 \_CRT\_NON\_CONFORMING\_WCSTOK를 정의하여 \_wcstok를 현재 위치에서 사용하도록 할 수 있습니다.  
  
### \<time.h\>  
  
-   **clock**  
  
     이전 버전에서 [clock](../c-runtime-library/reference/clock.md) 함수는 Windows API [GetSystemTimeAsFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724397.aspx)\(영문\)을 사용하여 구현되었습니다. 이 구현을 통해 clock 함수는 시스템 시간에 따라 달라지므로 단조일 필요가 없었습니다. clock 함수는 [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904.aspx)\(영문\)를 기준으로 다시 구현되었으며 현재는 단조입니다.  
  
-   **fstat 및 \_utime**  
  
     이전 버전에서 [\_stat](../c-runtime-library/reference/stat-functions.md), [fstat](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md) 및 [\_utime](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) 함수는 일광 절약 시간제를 잘못 처리합니다. Visual Studio 2013 이전에는 이들 함수가 모두 표준시 시간을 일광 절약 시간인 것처럼 잘못 조정했습니다.  
  
     Visual Studio 2013에서 이 문제는 \_stat 함수 패밀리에서 수정되었지만 fstat 및 \_utime 함수 패밀리에서는 비슷한 문제가 수정되지 않았습니다. 이로 인해 함수가 일치하지 않아 문제가 발생했습니다. 현재 fstat 및 \_utime 함수 패밀리가 수정되었으므로 현재 이들 함수는 모두 일광 절약 시간제를 올바르고 일관되게 처리합니다.  
  
-   **asctime**  
  
     이전 버전에서 [asctime](../c-runtime-library/reference/asctime-wasctime.md) 함수는 한 자리 일 단위의 앞에 0을 추가했습니다\(예: Fri Jun 06 08:00:00 2014\). 사양에 따라 해당 일 단위의 앞에는 공백이 추가되어야 합니다\(예: Fri Jun  6 08:00:00 2014\). 이 문제는 수정되었습니다.  
  
-   **strftime 및 wcsftime**  
  
     strftime 및 wcsftime 함수는 현재 %C, %D, %e, %F, %g, %G, %h, %n, %r, %R, %t, %T, %u 및 %V 서식 지정자를 지원합니다. 또한 E 및 O 수정자는 구문 분석되지만 무시됩니다.  
  
     %c 서식 지정자는 현재 로캘에 대한 "적절한 날짜 및 시간 표현"을 생성하도록 지정됩니다. C 로캘에서 이 표현은 %a %b %e %T %Y와 같아야 합니다. 이 표현은 asctime에서 생성된 것과 같은 형식입니다. 이전 버전에서 %c 서식 지정자는 MM\/DD\/YY HH:MM:SS 표현을 사용하여 시간 서식을 잘못 지정했습니다. 이 문제는 수정되었습니다.  
  
-   **timespec 및 TIME\_UTC**  
  
     현재 \<time.h\> 헤더는 C11 표준에 따라 timespec 형식 및 timespec\_get 함수를 정의합니다. 또한 현재 timespec\_get 함수와 함께 사용할 TIME\_UTC 매크로가 정의됩니다. 이는 이들에 대해 충돌하는 정의가 있는 코드의 주요 변경 내용입니다.  
  
-   **CLOCKS\_PER\_SEC**  
  
     현재 CLOCKS\_PER\_SEC 매크로는 C 언어에 필요한 형식 clock\_t의 정수로 확장됩니다.  
  
###  <a name="BK_STL"></a> 표준 템플릿 라이브러리  
 새로운 최적화 및 디버깅 검사를 사용하려면 C\+\+ 표준 라이브러리의 Visual Studio 구현은 버전별로 바이너리 호환성을 의도적으로 변경합니다. 따라서 C\+\+ 표준 라이브러리가 사용되면 서로 다른 버전을 사용하여 컴파일된 개체 파일 및 정적 라이브러리를 하나의 바이너리\(EXE 또는 DLL\)에 혼합할 수 없고 C\+\+ 표준 라이브러리 개체는 서로 다른 버전을 사용하여 컴파일된 바이너리 사이에서 전달할 수 없습니다. 그렇게 혼합하면 \_MSC\_VER 불일치에 대한 링커 오류를 내보냅니다. \_MSC\_VER은 컴파일러의 주 버전\(예: Visual Studio 2013의 경우 1800\)이 포함된 매크로입니다. 이 검사에서는 DLL 혼합을 비롯하여 Visual C\+\+ 2008 또는 이전 버전과 관련된 혼합을 감지할 수 없습니다.  
  
-   **STL include 파일**  
  
     STL 헤더의 include 구조체에 몇 가지 변경 내용이 적용되었습니다. STL 헤더는 서로 지정되지 않는 방식으로 포함할 수 있습니다. 일반적으로 C\+\+ 표준에 따라 필요한 모든 헤더를 신중하게 포함하고 다른 STL 헤더를 포함하는 STL 헤더를 사용하지 않도록 코드를 작성해야 합니다. 이렇게 하면 버전 및 플랫폼 간에 코드를 이식할 수 있습니다.[!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)]의 헤더 변경 내용 두 개 이상이 사용자 코드에 영향을 미칩니다. 첫 번째, \<string\>은 더 이상 \<iterator\>를 포함하지 않습니다. 두 번째, \<tuple\>은 현재 모든 \<array\>를 포함하지 않고 std::array를 선언하여 다음 생성자 구문 조합을 통해 코드를 분할합니다. 코드에 "array" 변수가 있고, using 지시문 "using namespace std;"를 포함하고, 현재 std::array를 선언하는 \<tuple\>이 포함된 STL 헤더\(예: \<functional\>\)를 포함합니다.  
  
-   **steady\_clock**  
  
     [steady\_clock](../standard-library/steady-clock-struct.md)의 \<chrono\> 구현은 지속성 및 단조성에 대한 C\+\+ 표준 요구 사항을 충족하도록 변경되었습니다. 이제 steady\_clock은 [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904.aspx)\(영문\)를 기반으로 하고 high\_resolution\_clock은 steady\_clock에 대한 typedef입니다. 따라서 Visual C\+\+에서 steady\_clock::time\_point는 현재 chrono::time\_point\<steady\_clock\>에 대한 typedef이나, 다른 구현에 이를 반드시 적용할 필요는 없습니다.  
  
-   **allocator 및 const**  
  
     현재 양쪽에서 const 인수를 수락하려면 allocator 같음\/같지 않음 비교가 필요합니다.  allocator가 이들 연산자를 다음과 같이 정의할 경우:  
  
    ```  
    bool operator==(const MyAlloc& other)  
    ```  
  
     이들 연산자를 업데이트하여 const 멤버로 선언해야 합니다.  
  
    ```  
    bool operator==(const MyAlloc& other) const  
    ```  
  
-   **const 요소**  
  
     C\+\+ 표준에서는 const 요소의 컨테이너\(예: vector\<const T\> 또는 set\<const T\>\)를 항상 금지했습니다. Visual C\+\+ 2013 이하에서는 해당 컨테이너를 허용했습니다. 현재 버전에서는 해당 컨테이너가 컴파일되지 않습니다.  
  
-   **std::allocator::deallocate**  
  
     Visual C\+\+ 2013 이하에서 std::allocator::deallocate\(p, n\)는 n으로 전달된 인수를 무시했습니다.  C\+\+ 표준에서 n은 항상 p를 반환한 allocate의 호출에 첫 번째 인수로 전달된 값과 같아야 합니다. 그러나현재 버전에서는 n 값이 검사됩니다. 표준에 필요한 값과 다른 n에 대한 인수를 전달하는 코드는 런타임에 충돌을 가져올 수 있습니다.  
  
-   **hash\_map 및 hash\_set**  
  
     비표준 헤더 파일 hash\_map 및 hash\_set은 [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)]에서 사용되지 않고 이후 릴리스에서 제거될 예정입니다. 대신에 unordered\_map 및 unordered\_set을 사용하세요.  
  
-   **비교 연산자 및 operator\(\)**  
  
     현재 연관 컨테이너\(\<map\> 패밀리\)에서 const 호출 가능 함수 호출 연산자를 포함하려면 비교 연산자가 필요합니다. 현재 비교 연산자 클래스 선언에서 다음 코드는 컴파일되지 않습니다.  
  
    ```  
    bool operator()(const X& a, const X& b)  
    ```  
  
     이 오류를 해결하려면 함수 선언을 다음으로 변경합니다.  
  
    ```  
    bool operator()(const X& a, const X& b) const  
    ```  
  
-   **형식 특성**  
  
     C\+\+ 초안 표준의 이전 버전에서 형식 특성의 이전 이름이 제거되었습니다. 이 이름은 C\+\+11에서 변경되었고 [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)]에서 C\+\+11 값으로 업데이트되었습니다. 다음 표에서는 이전 이름과 새 이름을 보여 줍니다.  
  
    |이전 이름|새 이름|  
    |-----------|----------|  
    |add\_reference|add\_lvalue\_reference|  
    |has\_default\_constructor|is\_default\_constructible|  
    |has\_copy\_constructor|is\_copy\_constructible|  
    |has\_move\_constructor|is\_move\_constructible|  
    |has\_nothrow\_constructor|is\_nothrow\_default\_constructible|  
    |has\_nothrow\_default\_constructor|is\_nothrow\_default\_constructible|  
    |has\_nothrow\_copy|is\_nothrow\_copy\_constructible|  
    |has\_nothrow\_copy\_constructor|is\_nothrow\_copy\_constructible|  
    |has\_nothrow\_move\_constructor|is\_nothrow\_move\_constructible|  
    |has\_nothrow\_assign|is\_nothrow\_copy\_assignable|  
    |has\_nothrow\_copy\_assign|is\_nothrow\_copy\_assignable|  
    |has\_nothrow\_move\_assign|is\_nothrow\_move\_assignable|  
    |has\_trivial\_constructor|is\_trivially\_default\_constructible|  
    |has\_trivial\_default\_constructor|is\_trivially\_default\_constructible|  
    |has\_trivial\_copy|is\_trivially\_copy\_constructible|  
    |has\_trivial\_move\_constructor|is\_trivially\_move\_constructible|  
    |has\_trivial\_assign|is\_trivially\_copy\_assignable|  
    |has\_trivial\_move\_assign|is\_trivially\_move\_assignable|  
    |has\_trivial\_destructor|is\_trivially\_destructible|  
  
-   **launch::any 및 launch::sync 정책**  
  
     비표준 launch::any 및 launch::sync 정책이 제거되었습니다. 대신에 launch::any의 경우 launch:async &#124; launch:deferred를 사용합니다. launch::sync의 경우 launch::deferred를 사용합니다.[launch 열거형](../Topic/launch%20Enumeration.md)을 참조하세요.  
  
###  <a name="BK_MFC"></a> MFC 및 ATL  
  
-   **MFC\(Microsoft Foundation Classes\)**는 큰 크기로 인해 더 이상 Visual Studio의 "일반" 설치에 포함되지 않습니다. MFC를 설치하려면 Visual Studio 2015 설치 프로그램에서 사용자 지정 설치 옵션을 선택합니다. Visual Studio 2015가 설치되어 있으면 Visual Studio 설치 프로그램을 다시 실행하고 사용자 지정 설치 옵션을 선택하고 Microsoft Foundation Classes를 선택하여 MFC를 설치할 수 있습니다. 제어판, 프로그램 및 기능에서 또는 설치 미디어에서 Visual Studio 설치 프로그램을 다시 실행할 수 있습니다.  
  
     Visual C\+\+ 재배포 가능 패키지에는 이 라이브러리가 계속 포함됩니다.  
  
###  <a name="BK_ConcRT"></a> 동시성 런타임  
  
-   **concurrency::Context::Yield와 충돌하는 Windows.h의 Yield 매크로입니다.**  
  
     이전 동시성 런타임은 Windows.h h에 정의된 Yield 매크로와 concurrency::Context::Yield 함수의 충돌을 피하려고 \#undef를 사용하여 Yield 매크로의 정의를 해제했습니다. 이 \#undef는 제거되었고 새로운 충돌하지 않는 동등한 API 호출 [concurrency::Context::YieldExecution](../Topic/Context::YieldExecution%20Method.md)이 추가되었습니다. Yield 충돌을 해결하려면 코드를 업데이트하여 대신 YieldExecution 함수를 호출하거나, 다음 예제와 같이 호출 쪽에서 Yield 함수 이름을 괄호로 묶습니다.  
  
    ```  
    (concurrency::Context::Yield)();  
    ```  
  
## 참고 항목  
 [시작](../misc/getting-started-with-visual-cpp-in-visual-studio-2015.md)   
 [Visual C\+\+ 2013의 주요 변경 내용](https://msdn.microsoft.com/library/hh409293.aspx)