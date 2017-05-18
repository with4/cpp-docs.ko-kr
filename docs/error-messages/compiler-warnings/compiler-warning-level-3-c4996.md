---
title: "컴파일러 경고 (수준 3) C4996 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 9a0c25772fadec86a893b8c7c4af09072eb0476f
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-3-c4996"></a>컴파일러 경고 (수준 3) C4996
컴파일러가 사용되지 않는 선언을 발견했습니다.  
  
이 경고 또는 오류는 컨텍스트에 따라 여러 가지 의미 합니다.  
  
컴파일러로 표시 된 변수 또는 함수에서 발생 하는 경우 c 4996 발생 [사용 되지 않는](../../cpp/deprecated-cpp.md) 를 사용 하 여는 `__declspec(deprecated)` 한정자. 이 경고는 함수, 클래스 멤버 또는 C + + 14가 있는 형식 정의 액세스 하려고 할 때에 발생 `[[deprecated]]` 특성입니다. 자세한 내용은 참조 [c + + 표준 특성](../../cpp/attributes2.md)합니다. 하는 데이 특성 직접 라이브러리에서 사용 되지 않는 함수, 멤버 또는 형식 정의 대 한 클라이언트에 게 경고 합니다.  
  
Visual Studio의 라이브러리에서 여러 함수, 멤버 함수, 템플릿 함수 및 전역 변수가 사용되지 않는 것으로 표시됩니다. 이러한 함수는 다른 기본 설정 이름을 갖거나, 안전하지 않거나 더 안전한 변형이 있거나, 구식일 수 있습니다. 많은 오류 메시지는 사용 되지 않는 함수 또는 전역 변수에 대 한 추천을 포함합니다.  
  
이 문제를 해결 하려면 일반적으로 권장 제안 된 안전 기능 또는 업데이트 된 함수 및 전역 변수를 대신 사용 하 여 코드를 변경 합니다. 이식성 이유로 기존 함수 또는 변수를 사용 해야 하는 경우 경고 해제할 수 있습니다.  
  
사용 하 여 특정 코드 줄에 대 한 경고를 해제할 수 있습니다는 [경고](../../preprocessor/warning.md) pragma `#pragma warning(suppress : 4996)`합니다. 있습니다 해제할 수 파일 내에서 경고 pragma를 사용 하 여 `#pragma warning(disable : 4996)`합니다. 해제할 수 있습니다이 전역으로 명령줄 빌드에 사용 하 여는 **/wd4996** 명령줄 옵션입니다. Visual Studio IDE에서 프로젝트에 대 한 경고를 해제 하려면 열고는 **속성 페이지** 대화 상자에서는 **구성 속성**, **C/c + +**, **고급** 페이지 및 편집는 **특정 경고 사용 안 함** 추가할 속성 `4996`합니다.  또한 특정 특정 클래스의 라이브러리에서 사용 되는 사용 중단 경고를 해제 하려면 전처리기 매크로 사용할 수 있습니다. 이러한 매크로 대 한 설명은 다음과 같습니다.  
  
다음은 c 4996의 라이브러리 원본 중 일부입니다.  
  
## <a name="posix-function-names"></a>POSIX 함수 이름  
  
**이 항목에 대 한 POSIX 이름은 사용 되지 않습니다. 대신 ISO C 및 c + + 규격 이름을 사용 하 여:** *new_name*합니다. **자세한 내용은 온라인 도움말을 참조 하십시오.**  
  
Microsoft의 C99 및 전역 함수 구현에서 정의 된 이름에 대 한 C + + 03 규칙을 준수 하도록 CRT의 일부 POSIX 함수 이름을 변경 합니다. 원래 POSIX 이름만 지원 되지 않습니다. 함수 자체입니다. 대부분의 경우 표준 규격 이름을 만들기 위해 POSIX 함수 이름에 선행 밑줄이 추가되었습니다. 컴파일러는 원래 함수 이름에 대 한 사용 중단 경고를 실행 하 고 기본 설정된 이름을 제안 합니다.  
  
이 문제를 해결 하려면 일반적으로 권장 대신 제안 된 함수 이름을 사용 하도록 코드를 변경 합니다. 그러나 업데이트 된 이름은 Microsoft 전용. 이식성 이유로 기존 함수 이름을 사용 해야 할 경우에 이러한 경고를 해제할 수 있습니다. POSIX 함수는 원래 이름 아래의 라이브러리 계속 사용할 수 있습니다.  
  
이러한 함수에 대한 사용 중단 경고를 끄려면 전처리기 매크로 **_CRT_NONSTDC_NO_WARNINGS**를 정의합니다. `/D_CRT_NONSTDC_NO_WARNINGS`옵션을 포함하여 명령줄에서 이 매크로를 정의할 수 있습니다. Visual Studio에서 이 매크로를 정의하려면 프로젝트에 대한 **속성 페이지** 대화 상자를 엽니다. **구성 속성**, **C/C++**, **전처리기**를 차례로 확장합니다. **전처리기 정의**에서 `_CRT_NONSTDC_NO_WARNINGS`를 추가합니다. **확인** 을 선택하여 저장한 다음 프로젝트를 다시 빌드합니다. 특정 원본 파일에서만 이 매크로를 정의하려면 헤더 파일이 포함된 모든 줄 앞에 `#define _CRT_NONSTDC_NO_WARNINGS` 줄을 추가합니다.  
  
## <a name="unsafe-crt-library-functions"></a>안전 하지 않은 CRT 라이브러리 함수  
  
 **이 함수 또는 변수 안전 하지 않을 수 있습니다. 사용 하는 것이 좋습니다***safe_version* **대신 합니다.   사용 중단을 사용하지 않도록 설정하려면 _CRT_SECURE_NO_WARNINGS를 사용합니다.  자세한 내용은 온라인 도움말을 참조하세요.**  
  
 일부 CRT 및 c + + 표준 라이브러리 함수 및 전역 변수에 더 안전한 버전을 위해 Microsoft는 사용 되지 않습니다. 대부분의 경우 사용 되지 않는 함수 검사 되지 않은 읽기 또는 심각한 보안 문제가 발생할 수 있습니다 이러한 버퍼에 대 한 쓰기 액세스를 허용 합니다. 컴파일러는 이러한 함수에 대해 사용 중단 경고를 실행하고 기본 설정 함수를 제안합니다.  
  
 이 문제를 해결 하려면 함수 또는 변수를 사용 하면 권장 *safe_version* 대신 합니다. 버퍼 덮어쓰기 불가능 또는 사용자 코드에서 발생 하도록 overread 이식성 원인에 대 한 코드를 변경할 수 없습니다를 확인 한 경우 경고를 해제할 수 있습니다.  
   
 CRT에서 이러한 함수에 대한 사용 중단 경고를 끄려면 **_CRT_SECURE_NO_WARNINGS**를 정의합니다. 사용되지 않는 전역 변수에 대한 경고를 끄려면 **_CRT_SECURE_NO_WARNINGS_GLOBALS**를 정의합니다. 이러한 사용 되지 않는 함수 및 전역 변수에 대 한 자세한 내용은 참조 하십시오. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 및 [안전한 라이브러리: c + + 표준 라이브러리](../../standard-library/safe-libraries-cpp-standard-library.md)합니다.  
  
## <a name="unsafe-standard-library-functions"></a>안전 하지 않은 표준 라이브러리 함수  
  
 **' std::** *function_name* **::\_옵션을 해제\_반복기::\_Deprecate' 호출 std::** *function_name* **안전 하지 않을 수 있는 매개 변수와 함께이 호출은 전달 된 값이 정확한 지 확인 하려면 호출자에 의존 합니다. 이 경고를 사용하지 않으려면 -D_SCL_SECURE_NO_WARNINGS를 사용합니다. Visual c + + ' 확인 된 반복기 ' 사용 하는 방법에 설명서를 참조 하십시오.**  
  
이 경고는 특정 c + + 표준 라이브러리 템플릿 함수는 매개 변수의 정확성을 검사 하지 않습니다 때문에 디버그 빌드에 나타납니다. 대부분의 경우에서이 정보가 충분 하지 않음 컨테이너 범위를 확인 하는 함수를 사용할 수 있으므로 되거나 함수 사용 하 여 반복기를 올바르게 사용할 수 있습니다 있습니다. 프로그램에서 보안 허점의 원본을 수 있기 때문에이 경고는 이러한 함수의 사용을 확인할 수 있습니다. 자세한 내용은 [Checked Iterators](../../standard-library/checked-iterators.md)을 참조하세요.  
  
한 요소 포인터를 전달 하는 경우이 경고 디버그 모드로 표시 예를 들어 `std::copy` 일반 배열 대신 합니다. 이 문제를 해결 하려면 라이브러리 수 배열 익스텐트를 확인 하 고 범위 검사를 수행 하므로 적절 하 게 선언 된 배열을 사용 합니다.  
  
```cpp  
// C4996_copyarray.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_copyarray.cpp
#include <algorithm>
 
void example(char const * const src) { 
    char dest[1234]; 
    char * pdest3 = dest + 3;
    std::copy(src, src + 42, pdest3); // C4996 
    std::copy(src, src + 42, dest);   // OK, copy can tell that dest is 1234 elements 
} 
```  
  
여러 표준 라이브러리 알고리즘은 C + + 14에서 "이중 범위" 버전을 보유 하도록 업데이트 되었습니다. 이중 범위 버전을 사용 하는 경우 두 번째 범위는 필요한 범위를 검사를 제공 합니다.  
  
```cpp  
// C4996_containers.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_containers.cpp
#include <algorithm>
 
bool example(
    char const * const left, 
    const size_t leftSize, 
    char const * const right, 
    const size_t rightSize) 
{ 
    bool result = false;
    result = std::equal(left, left + leftSize, right); // C4996
    // To fix, try this form instead: 
    // result = std::equal(left, left + leftSize, right, right + rightSize); // OK 
    return result;
}
```  
  
이 예제에서는 더 많은 여러 가지 방법으로 표준 라이브러리를 사용 하 여 반복기 사용을 확인 수 및 확인 되지 않은 사용 위험할 수 있습니다.  
  
```cpp  
// C4996_standard.cpp
// compile with: cl /EHsc /W4 /MDd C4996_standard.cpp
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
    // (i.e. an overrun triggers a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun triggers a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (i.e. an overrun triggers a debug assertion)  
    // NOTE: This applies only when raw arrays are 
    // given to C++ Standard Library algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (i.e. an overrun triggers undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (i.e. an overrun triggers a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), 
        stdext::make_checked_array_iterator(p7, 16), 
        [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator 
    // is marked as checked in debug mode, but it performs no checking, 
    // so an overrun triggers undefined behavior  
    int a8[16];  
    int * p8 = a8;  
    transform( v.begin(), v.end(), 
        stdext::make_unchecked_array_iterator(p8), 
        [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
```  
  
코드 버퍼 오버런이 경고를 트리거하는 표준 라이브러리 함수에서 오류를 가질 수 없음을 확인 한 경우에이 경고를 해제 하는 것이 좋습니다. 이러한 함수에 대한 경고를 끄려면 **_SCL_SECURE_NO_WARNINGS**를 정의합니다.   
  
## <a name="example-checked-iterators-enabled"></a>예: 확인 된 반복기 사용  
  
로 컴파일할 때 확인 된 반복기를 사용 하지 않는 경우에 c 4996 발생할 수 있습니다 `_ITERATOR_DEBUG_LEVEL` 1 또는 2로 정의 합니다. 디버그 모드 빌드의 경우 기본적으로 2 하 고 일반 정품 빌드에 대 한 0으로 설정 됩니다. 자세한 내용은 [Checked Iterators](../../standard-library/checked-iterators.md) 를 참조하세요.  
  
```cpp  
// C4996_checked.cpp  
// compile with: /EHsc /W4 /MDd C4996_checked.cpp  
#define _ITERATOR_DEBUG_LEVEL 2  
  
#include <algorithm>  
#include <iterator>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
    int a[] = { 1, 2, 3 };  
    int b[] = { 10, 11, 12 };  
    copy(a, a + 3, b + 1);   // C4996  
    // try the following line instead:  
    // copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK  
}  
```  
  
## <a name="unsafe-mfc-or-atl-code"></a>안전 하지 않은 MFC 또는 ATL 코드  
  
C 4996 보안상의 이유로 더 이상 사용 되지 않는 MFC 나 ATL 함수를 사용 하는 경우에 발생할 수 있습니다.  
  
이 문제를 해결 하려면 대신 업데이트 된 함수를 사용 하도록 코드를 변경한 것이 좋습니다.  
  
이러한 경고를 표시 하는 방법에 대 한 정보를 참조 하십시오. [_AFX_SECURE_NO_WARNINGS](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings) 및 [_ATL_SECURE_NO_WARNINGS](http://msdn.microsoft.com/Library/587d29d8-a75a-44a3-bec8-f724087e5e73)합니다.  
  
## <a name="obsolete-crt-functions-and-variables"></a>사용 되지 않는 CRT 함수 및 변수  
  
**이 함수 또는 변수 최신 라이브러리 또는 운영 체제 기능으로 대체 되었습니다. 사용 하는 것이 좋습니다** *new_item* **대신 합니다. 자세한 내용은 온라인 도움말을 참조하세요.**  
  
일부 라이브러리 함수 및 전역 변수는 구식으로 사용되지 않습니다. 이러한 함수 및 변수는 이후 버전의 라이브러리에서 제거될 수도 있습니다. 컴파일러는 이러한 항목에 대해 사용 중단 경고를 실행하고 기본 설정 대체 항목을 제안합니다.  
  
이 문제를 해결 하려면 제안 된 함수 또는 변수를 사용 하 여 코드를 변경 하는 것이 좋습니다.  
  
이러한 항목에 대한 사용 중단 경고를 끄려면 **_CRT_OBSOLETE_NO_WARNINGS**를 정의합니다. 자세한 내용은 사용되지 않는 함수 또는 변수에 대한 설명서를 참조하세요.  
  
## <a name="example-marshalling-errors-in-clr-code"></a>예: 코드의 마샬링 오류 CLR  
  
C 4996은 CLR 마샬링 라이브러리를 사용 하는 경우에 발생할 수 있습니다. 이 경우 C4996은 경고가 아니라 오류입니다. 이 오류를 사용할 때 발생 [marshal_as](../../dotnet/marshal-as.md) 해야 하는 두 개의 데이터 형식 간에 변환 하는 [marshal_context 클래스](../../dotnet/marshal-context-class.md)합니다. 마샬링 라이브러리가 변환을 지원 하지 않을 때에이 오류를 받을 수 있습니다. 마샬링 라이브러리에 대한 자세한 내용은 [Overview of Marshaling in C++](../../dotnet/overview-of-marshaling-in-cpp.md)를 참조하세요.  
  
마샬링 라이브러리에서 변환 하는 컨텍스트가 필요 하기 때문에이 예제에서는 c 4996이 생성 한 `System::String` 에 `const char *`합니다.  
  
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
  
## <a name="example-user-defined-deprecated-function"></a>예: 사용 되지 않는 사용자 정의 함수  
  
더 이상 특정 함수의 사용을 권장 하는 경우 호출자에 게 경고를 사용자 코드에서 사용 되지 않는 특성을 사용할 수 없습니다. 이 예제에서는 c 4996은 함수를 사용 하는 줄과 행으로 사용 되지 않는 함수 선언 되는 설정에 대 한 생성 됩니다.  
  
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
   func1(1);    // C4996  
}  
```  
  

