---
title: "컴파일러 경고 (수준 3) C4996 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4996"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4996"
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
caps.latest.revision: 34
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 34
---
# 컴파일러 경고 (수준 3) C4996
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러가 사용되지 않는 선언을 발견했습니다.  
  
 이 경고 또는 오류는 여러 가지 의미를 가질 수 있습니다.  
  
 컴파일러가 [사용되지 않음](../../cpp/deprecated-cpp.md)으로 표시된 함수 또는 변수를 발견할 경우 `C4996`이 발생합니다. Visual Studio의 라이브러리에서 여러 함수, 멤버 함수, 템플릿 함수 및 전역 변수가 사용되지 않는 것으로 표시됩니다. 이러한 함수는 다른 기본 설정 이름을 갖거나, 안전하지 않거나 더 안전한 변형이 있거나, 구식일 수 있습니다. 오류 메시지는 사용되지 않는 함수 또는 전역 변수에 대해 제안되는 대체 항목을 포함할 수도 있습니다. 다음 예제와 같이 [warning](../../preprocessor/warning.md) pragma 또는 **\/wd4996** 명령줄 옵션을 사용하여 이 경고를 끌 수 있습니다. 전처리기 매크로를 사용하여 특정 클래스의 사용 중단 경고를 끌 수도 있습니다.  
  
 **이 항목에 대한 POSIX 이름은 사용되지 않습니다. 대신, ISO C 및 C\+\+ 규칙에 부합되는 이름\(** new\_name**\)을 사용합니다. 자세한 내용은 온라인 도움말을 참조하세요.**  
  
 구현에서 정의된 전역 함수 이름에 대한 C99 및 C\+\+03 규칙을 준수하기 위해 CRT의 일부 POSIX 함수 이름이 바뀌었습니다. 대부분의 경우 표준 규격 이름을 만들기 위해 POSIX 함수 이름에 선행 밑줄이 추가되었습니다. 컴파일러는 원래 함수 이름에 대해 사용 중단 경고를 실행하고 기본 설정 이름을 제안합니다. 원래 이름만 사용되지 않고 함수 자체는 사용됩니다. 이러한 함수에 대한 사용 중단 경고를 끄려면 전처리기 매크로 **\_CRT\_NONSTDC\_NO\_WARNINGS**를 정의합니다. `/D_CRT_NONSTDC_NO_WARNINGS` 옵션을 포함하여 명령줄에서 이 매크로를 정의할 수 있습니다. Visual Studio에서 이 매크로를 정의하려면 프로젝트에 대한 **속성 페이지** 대화 상자를 엽니다.**구성 속성**, **C\/C\+\+**, **전처리기**를 차례로 확장합니다.**전처리기 정의**에서 `_CRT_NONSTDC_NO_WARNINGS`를 추가합니다.**확인**을 선택하여 저장한 다음 프로젝트를 다시 빌드합니다. 특정 원본 파일에서만 이 매크로를 정의하려면 헤더 파일이 포함된 모든 줄 앞에 `#define _CRT_NONSTDC_NO_WARNINGS` 줄을 추가합니다.  
  
 **이 함수 또는 변수는 안전하지 않을 수 있습니다.** safe\_version**을 대신 사용하는 것이 좋습니다. 사용 중단을 사용하지 않도록 설정하려면 \_CRT\_SECURE\_NO\_WARNINGS를 사용합니다.  자세한 내용은 온라인 도움말을 참조하세요.**  
  
 일부 CRT 및 표준 C\+\+ 라이브러리 함수와 전역 변수는 보안이 강화된 새 함수로 대체되어 더 이상 사용되지 않습니다. 컴파일러는 이러한 함수에 대해 사용 중단 경고를 실행하고 기본 설정 함수를 제안합니다. CRT에서 이러한 함수에 대한 사용 중단 경고를 끄려면 **\_CRT\_SECURE\_NO\_WARNINGS**를 정의합니다. 사용되지 않는 전역 변수에 대한 경고를 끄려면 **\_CRT\_SECURE\_NO\_WARNINGS\_GLOBALS**를 정의합니다. 이러한 사용되지 않는 함수 및 전역 변수에 대한 자세한 내용은 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 및 [안전한 라이브러리: C\+\+ 표준 라이브러리](../../standard-library/safe-libraries-cpp-standard-library.md)를 참조하세요.  
  
 **안전하지 않을 수 있는 매개 변수를 사용하는 함수 호출이며, 이 호출은 호출자가 전달된 값이 올바른지 확인하는 것에 의존합니다. 이 경고를 사용하지 않으려면 \-D\_SCL\_SECURE\_NO\_WARNINGS를 사용합니다. Visual C\+\+ '확인된 반복기' 사용 방법에 대한 설명서를 참조하십시오.**  
  
 특정 C\+\+ 표준 라이브러리 템플릿 함수는 매개 변수의 정확성을 검사하지 않습니다. 이 경고는 이러한 함수의 사용을 식별하는 데 도움이 됩니다. 이러한 함수에 대한 경고를 끄려면 **\_SCL\_SECURE\_NO\_WARNINGS**를 정의합니다. 자세한 내용은 [Checked Iterators](../../standard-library/checked-iterators.md)을 참조하세요.  
  
 **이 함수 또는 변수는 최신 라이브러리 또는 운영 체제 기능으로 대체되었습니다.** new\_item**을 대신 사용하는 것이 좋습니다. 자세한 내용은 온라인 도움말을 참조하세요.**  
  
 일부 라이브러리 함수 및 전역 변수는 구식으로 사용되지 않습니다. 이러한 함수 및 변수는 이후 버전의 라이브러리에서 제거될 수도 있습니다. 컴파일러는 이러한 항목에 대해 사용 중단 경고를 실행하고 기본 설정 대체 항목을 제안합니다. 이러한 항목에 대한 사용 중단 경고를 끄려면 **\_CRT\_OBSOLETE\_NO\_WARNINGS**를 정의합니다. 자세한 내용은 사용되지 않는 함수 또는 변수에 대한 설명서를 참조하세요.  
  
 **MFC 또는 ATL 코드의 다양한 메시지**  
  
 보안상의 이유로 더 이상 사용되지 않는 MFC나 ATL 함수를 사용하는 경우에도 `C4996`이 발생할 수 있습니다. 이러한 경고를 표시하지 않으려면 [\_AFX\_SECURE\_NO\_WARNINGS](../Topic/_AFX_SECURE_NO_WARNINGS.md) 및 [\_ATL\_SECURE\_NO\_WARNINGS](../Topic/_ATL_SECURE_NO_WARNINGS.md)를 참조하세요.  
  
 **CLR 코드의 마샬링 오류**  
  
 또한 `C4996`은 마샬링 라이브러리를 사용할 때 발생할 수 있습니다. 이 경우 C4996은 경고가 아니라 오류입니다. 이 오류는 [marshal\_context 클래스](../../dotnet/marshal-context-class.md)가 필요한 두 데이터 형식 간의 변환을 위해 [marshal\_as](../../dotnet/marshal-as.md)를 사용할 때 발생합니다. 마샬링 라이브러리가 변환을 지원하지 않을 때 이 오류가 발생하기도 합니다. 마샬링 라이브러리에 대한 자세한 내용은 [C\+\+ 마샬링 개요](../../dotnet/overview-of-marshaling-in-cpp.md)를 참조하세요.  
  
 **C4996 생성 예제**  
  
 첫 번째 예제에서 `C4996`은 함수를 선언한 줄과 사용한 줄에서 발생합니다.  
  
## 예제  
 다음 샘플에서는 C4996을 생성합니다.  
  
```cpp  
// C4996.cpp // compile with: /W3 // C4996 warning expected #include <stdio.h> // #pragma warning(disable : 4996) void func1(void) { printf_s("\nIn func1"); } __declspec(deprecated) void func1(int) { printf_s("\nIn func2"); } int main() { func1(); func1(1); }  
```  
  
## 예제  
 또한 C4996은 `_ITERATOR_DEBUG_LEVEL`를 정의한 상태에서\(디버그 모드 빌드의 경우 기본적으로 1로 설정\) 컴파일할 때 확인된 반복기를 사용하지 않는 경우에 발생할 수 있습니다.  자세한 내용은 [Checked Iterators](../../standard-library/checked-iterators.md)를 참조하세요.  
  
 다음 STL 코드 예제에서는 C4996이 생성됩니다.  
  
```cpp  
// C4996_b.cpp // compile with: /EHsc /W3 /c #define _ITERATOR_DEBUG_LEVEL 1 #include <algorithm> #include <iterator> using namespace std; using namespace stdext; int main() { int a[] = { 1, 2, 3 }; int b[] = { 10, 11, 12 }; copy(a, a + 3, b + 1);   // C4996 // try the following line instead //   copy(a, a + 3, b); copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK }  
  
```  
  
## 예제  
 다음 STL 코드 예제에서는 C4996이 경고로 생성됩니다. 주석은 인라인입니다.  
  
```cpp  
#include <algorithm> #include <array> #include <iostream> #include <iterator> #include <numeric> #include <string> #include <vector> using namespace std; template <typename C> void print(const string& s, const C& c) { cout << s; for (const auto& e : c) { cout << e << " "; } cout << endl; } int main() { vector<int> v(16); iota(v.begin(), v.end(), 0); print("v: ", v); // OK: vector::iterator is checked in debug mode // (i.e. an overrun will trigger a debug assertion) vector<int> v2(16); transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; }); print("v2: ", v2); // OK: back_insert_iterator is marked as checked in debug mode // (i.e. an overrun is impossible) vector<int> v3; transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; }); print("v3: ", v3); // OK: array::iterator is checked in debug mode // (i.e. an overrun will trigger a debug assertion) array<int, 16> a4; transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; }); print("a4: ", a4); // OK: Raw arrays are checked in debug mode // (i.e. an overrun will trigger a debug assertion) // NOTE: This applies only when raw arrays are given to STL algorithms! int a5[16]; transform(v.begin(), v.end(), a5, [](int n) { return n * 5; }); print("a5: ", a5); // WARNING C4996: Pointers cannot be checked in debug mode // (i.e. an overrun will trigger undefined behavior) int a6[16]; int * p6 = a6; transform(v.begin(), v.end(), p6, [](int n) { return n * 6; }); print("a6: ", a6); // OK: stdext::checked_array_iterator is checked in debug mode // (i.e. an overrun will trigger a debug assertion) int a7[16]; int * p7 = a7; transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; }); print("a7: ", a7); // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode // (i.e. it performs no checking, so an overrun will trigger undefined behavior) int a8[16]; int * p8 = a8; transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; }); print("a8: ", a8); }  
  
```  
  
## 예제  
 마샬링 라이브러리에 `System::String`에서 `const char *`로 변환하는 컨텍스트가 필요하기 때문에 다음 샘플에서는 C4996 경고가 생성됩니다.  
  
```cpp  
// C4996_Marshal.cpp // compile with: /clr // C4996 expected #include <stdlib.h> #include <string.h> #include <msclr\marshal.h> using namespace System; using namespace msclr::interop; int main() { String^ message = gcnew String("Test String to Marshal"); const char* result; result = marshal_as<const char*>( message ); return 0; }  
```