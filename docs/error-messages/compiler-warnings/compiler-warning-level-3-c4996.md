---
title: "컴파일러 경고 (수준 3) C4996 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4996
dev_langs:
- C++
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
caps.latest.revision: 34
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: 4a82bbdd3b28ae0150ab8366d3ecbe849e7ac8a1
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4996"></a>컴파일러 경고 (수준 3) C4996
컴파일러가 사용되지 않는 선언을 발견했습니다.  
  
 이 경고 또는 오류는 여러 가지 의미를 가질 수 있습니다.  
  
 `C4996`컴파일러로 표시 된 변수 또는 함수에서 발생 하는 경우에 발생 [사용 되지 않는](../../cpp/deprecated-cpp.md)합니다. Visual Studio의 라이브러리에서 여러 함수, 멤버 함수, 템플릿 함수 및 전역 변수가 사용되지 않는 것으로 표시됩니다. 이러한 함수는 다른 기본 설정 이름을 갖거나, 안전하지 않거나 더 안전한 변형이 있거나, 구식일 수 있습니다. 오류 메시지는 사용되지 않는 함수 또는 전역 변수에 대해 제안되는 대체 항목을 포함할 수도 있습니다. 해제할 수 있습니다이 경고와는 [경고](../../preprocessor/warning.md) pragma 또는 **/wd4996** 명령줄 옵션입니다. 전처리기 매크로를 사용하여 특정 클래스의 사용 중단 경고를 끌 수도 있습니다. 

이 경고는 함수, 클래스 멤버 또는 C + + 14가 있는 형식 정의 액세스 하려고 할 때에 발생 `[[deprecated]]` 특성입니다. 자세한 내용은 참조 [c + + 표준 특성](../../cpp/attributes2.md)합니다. 
  
 **이 항목에 대 한 POSIX 이름은 사용 되지 않습니다. 대신 ISO C 및 c + + 규격 이름을 사용 하 여:** new_name**합니다. 자세한 내용은 온라인 도움말을 참조하세요.**  
  
 구현에서 정의된 전역 함수 이름에 대한 C99 및 C++03 규칙을 준수하기 위해 CRT의 일부 POSIX 함수 이름이 바뀌었습니다. 대부분의 경우 표준 규격 이름을 만들기 위해 POSIX 함수 이름에 선행 밑줄이 추가되었습니다. 컴파일러는 원래 함수 이름에 대해 사용 중단 경고를 실행하고 기본 설정 이름을 제안합니다. 원래 이름만 사용되지 않고 함수 자체는 사용됩니다. 이러한 함수에 대한 사용 중단 경고를 끄려면 전처리기 매크로 **_CRT_NONSTDC_NO_WARNINGS**를 정의합니다. `/D_CRT_NONSTDC_NO_WARNINGS`옵션을 포함하여 명령줄에서 이 매크로를 정의할 수 있습니다. Visual Studio에서 이 매크로를 정의하려면 프로젝트에 대한 **속성 페이지** 대화 상자를 엽니다. **구성 속성**, **C/C++**, **전처리기**를 차례로 확장합니다. **전처리기 정의**에서 `_CRT_NONSTDC_NO_WARNINGS`를 추가합니다. **확인** 을 선택하여 저장한 다음 프로젝트를 다시 빌드합니다. 특정 원본 파일에서만 이 매크로를 정의하려면 헤더 파일이 포함된 모든 줄 앞에 `#define _CRT_NONSTDC_NO_WARNINGS` 줄을 추가합니다.  
  
 **이 함수 또는 변수 안전 하지 않을 수 있습니다. 사용 하는 것이 좋습니다** safe_version **대신 합니다. 사용 중단을 사용하지 않도록 설정하려면 _CRT_SECURE_NO_WARNINGS를 사용합니다.  자세한 내용은 온라인 도움말을 참조하세요.**  
  
 일부 CRT 및 c + + 표준 라이브러리 함수 및 전역 변수 사용이 중단 된 더 안전한 새 함수로 대체 합니다. 컴파일러는 이러한 함수에 대해 사용 중단 경고를 실행하고 기본 설정 함수를 제안합니다. CRT에서 이러한 함수에 대한 사용 중단 경고를 끄려면 **_CRT_SECURE_NO_WARNINGS**를 정의합니다. 사용되지 않는 전역 변수에 대한 경고를 끄려면 **_CRT_SECURE_NO_WARNINGS_GLOBALS**를 정의합니다. 이러한 사용 되지 않는 함수 및 전역 변수에 대 한 자세한 내용은 참조 하십시오. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 및 [안전한 라이브러리: c + + 표준 라이브러리](../../standard-library/safe-libraries-cpp-standard-library.md)합니다.  
  
 **안전 하지 않을 수 있는 매개 변수를 사용 하 여 함수 호출이이 호출이 호출자가 전달 된 값이 올바른지 확인 하는 사용 합니다. 이 경고를 사용하지 않으려면 -D_SCL_SECURE_NO_WARNINGS를 사용합니다. Visual c + + ' 확인 된 반복기 ' 사용 하는 방법에 설명서를 참조 하십시오.**  
  
 특정 C++ 표준 라이브러리 템플릿 함수는 매개 변수의 정확성을 검사하지 않습니다. 이 경고는 이러한 함수의 사용을 식별하는 데 도움이 됩니다. 이러한 함수에 대한 경고를 끄려면 **_SCL_SECURE_NO_WARNINGS**를 정의합니다. 자세한 내용은 [확인된 반복기](../../standard-library/checked-iterators.md)를 참조하세요.  
  
 **이 함수 또는 변수 최신 라이브러리 또는 운영 체제 기능으로 대체 되었습니다. 사용 하는 것이 좋습니다** new_item **대신 합니다. 자세한 내용은 온라인 도움말을 참조하세요.**  
  
 일부 라이브러리 함수 및 전역 변수는 구식으로 사용되지 않습니다. 이러한 함수 및 변수는 이후 버전의 라이브러리에서 제거될 수도 있습니다. 컴파일러는 이러한 항목에 대해 사용 중단 경고를 실행하고 기본 설정 대체 항목을 제안합니다. 이러한 항목에 대한 사용 중단 경고를 끄려면 **_CRT_OBSOLETE_NO_WARNINGS**를 정의합니다. 자세한 내용은 사용되지 않는 함수 또는 변수에 대한 설명서를 참조하세요.  
  
 **MFC 또는 ATL 코드의 다양 한 메시지**  
  
 보안상의 이유로 더 이상 사용되지 않는 MFC나 ATL 함수를 사용하는 경우에도 `C4996`이 발생할 수 있습니다. 이러한 경고를 표시 하지 않으려면 참조 [_AFX_SECURE_NO_WARNINGS](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings) 및 [_ATL_SECURE_NO_WARNINGS](http://msdn.microsoft.com/Library/587d29d8-a75a-44a3-bec8-f724087e5e73)합니다.  
  
 **CLR 코드의 마샬링 오류**  
  
 또한 `C4996`은 마샬링 라이브러리를 사용할 때 발생할 수 있습니다. 이 경우 C4996은 경고가 아니라 오류입니다. 사용 하는 경우이 오류가 발생 합니다 [marshal_as](../../dotnet/marshal-as.md) 해야 하는 두 개의 데이터 형식 간에 변환 하는 [marshal_context 클래스](../../dotnet/marshal-context-class.md)합니다. 마샬링 라이브러리가 변환을 지원하지 않을 때 이 오류가 발생하기도 합니다. 마샬링 라이브러리에 대 한 자세한 내용은 참조 [개요의 c + + 마샬링](../../dotnet/overview-of-marshaling-in-cpp.md)합니다.  
  
 **C4996 생성 예제**  
  
 첫 번째 예제에서 `C4996` 은 함수를 선언한 줄과 사용한 줄에서 발생합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4996을 생성합니다.  
  
```cpp  
// C4996.cpp  
// compile with: /W3  
// C4996 warning expected  
#include <stdio.h>  
  
// #pragma warning(disable : 4996)  
void func1(void) {  
   printf_s("\nIn func1");  
}  
  
__declspec(deprecated) void func1(int) {  
   printf_s("\nIn func2");  
}  
  
int main() {  
   func1();  
   func1(1);  
}  
```  
  
## <a name="example"></a>예제  
 또한 C4996은 `_ITERATOR_DEBUG_LEVEL` 를 정의한 상태에서(디버그 모드 빌드의 경우 기본적으로 1로 설정) 컴파일할 때 확인된 반복기를 사용하지 않는 경우에 발생할 수 있습니다.  자세한 내용은 [확인된 반복기](../../standard-library/checked-iterators.md)를 참조하세요.  
  
 다음 c + + 표준 라이브러리의 코드 예제에서는 c 4996을 생성합니다.  
  
```cpp  
// C4996_b.cpp  
// compile with: /EHsc /W3 /c  
#define _ITERATOR_DEBUG_LEVEL 1  
  
#include <algorithm>  
#include <iterator>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
    int a[] = { 1, 2, 3 };  
    int b[] = { 10, 11, 12 };  
    copy(a, a + 3, b + 1);   // C4996  
    // try the following line instead  
    //   copy(a, a + 3, b);  
    copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK  
}  
  
```  
  
## <a name="example"></a>예제  
 다음 c + + 표준 라이브러리의 코드 예제에서는 경고로 c 4996을 생성합니다. 주석은 인라인입니다.  
  
```cpp  
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
    // (i.e. an overrun will trigger a debug assertion)  
    // NOTE: This applies only when raw arrays are given to C++ Standard Library algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (i.e. an overrun will trigger undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode  
    // (i.e. it performs no checking, so an overrun will trigger undefined behavior)  
    int a8[16];  
    int * p8 = a8;  
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
  
```  
  
## <a name="example"></a>예제  
 마샬링 라이브러리에 `System::String` 에서 `const char *`로 변환하는 컨텍스트가 필요하기 때문에 다음 샘플에서는 C4996 경고가 생성됩니다.  
  
```cpp  
// C4996_Marshal.cpp  
// compile with: /clr   
// C4996 expected  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = marshal_as<const char*>( message );  
   return 0;  
}  
```

