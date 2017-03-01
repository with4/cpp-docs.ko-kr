---
title: "링커 도구 오류 LNK2019 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2019
dev_langs:
- C++
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.assetid: 4392be92-195c-4eb2-bd4d-49cfac3ca291
caps.latest.revision: 39
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
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 86b43f2688b6e1dbfb39dfec681ca9adafd2c093
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2019"></a>링커 도구 오류 LNK2019
'symbol' 외부 기호(참조 위치: ' function' 함수)를 확인할 수 없습니다.  
  
 링커가 "`symbol`" 함수에 사용된 "`function`" 외부 기호에 대한 정의를 찾을 수 없습니다.  
  
 이 오류를 일으킬 수 있는 문제는 여러 가지입니다. 이 항목은 원인을 파악하고 해결책을 찾는 데 도움이 됩니다.  
  
 A *기호* 함수 또는 전역 변수를 사용 하 여 컴파일러의 이름입니다. *외부 기호* 다른 원본 또는 목적 물 파일에 정의 된 기호를 참조 하는 데 사용 하는 이름입니다. 링커 해야 *해결*, 또는 모든 함수 또는 응용 프로그램 또는 DLL에 연결 될 때 컴파일된 각 파일에서 사용 하는 전역 변수에 대 한 외부 기호에 대해 정의 찾습니다. 연결된 파일에서 외부 기호에 대해 일치하는 정의를 찾을 수 없는 경우 링커는 LNK2019를 생성합니다.  
  
 이 오류는 기호 정의가 있는 개체 또는 라이브러리 파일이 빌드에 포함 되지 않은 경우에 발생할 수 있습니다. 또한 링커가 검색에 대 한 기호 이름을 정의 하는 개체 또는 라이브러리 파일의 기호 이름과 일치 하지 않는 경우에 발생할 수 있습니다. 이 호출 코드에서 이름 철자가, 다른 대/소문자를 사용 하 여, 다른 호출 규칙을 사용 하 여 또는 다른 매개 변수를 지정 하는 경우에 발생할 수 있습니다.  
  
 C + + 링크를 사용 하는 코드를 사용 하 여 [이름 데코레이션](../../error-messages/tool-errors/name-decoration.md)라고도 *이름 장식*는 변수 또는 함수 유형 및 기호 이름에 대 한 호출 규칙에 대 한 추가 정보를 인코딩합니다. *트데코레이된 이름* 은 링커가 외부 기호를 확인하기 위해 검색하는 이름입니다. 형식 정보를 사용 하면 기호의 데코레이팅된 이름의 일부가, 때문에 사용 되는 위치는 외부 기호의 선언에 정의 된 기호 선언의 일치 하지 않는 경우 n k&2019;가 발생할 수 있습니다. 을 오류의 원인을 찾을 수 있도록 오류 메시지 모두 "친숙 한 이름을 표시," 소스 코드 및 확인 되지 않은 외부 기호에 대 한 괄호 안에 데코레이팅된 이름을 사용 하는 이름입니다. 다른 데코레이팅된 이름과 비교할 수 있어야 하는 데코레이팅된 이름을 변환 하는 방법을 알고 필요가 없습니다.  
  
 **일반적인 문제**  
  
 LNK2019를 일으키는 일반적인 문제는 다음과 같습니다.  
  
-   **개체 파일 또는 기호 정의 포함 하는 라이브러리 연결 되지 않습니다.** Visual Studio에서 정의 포함 하는 소스 파일의 프로젝트의 일환으로 연결 된 빌드를 확인 합니다. 명령줄에서 정의 포함 하는 소스 파일을 컴파일한 있으며 결과 개체 파일에 연결 하는 파일의 목록에 포함 되어 있는지 확인 합니다.  
  
-   **기호 선언의 기호 정의 동일 철자가 수 있습니다.** 올바른 철자 및 대/소문자는 선언 및 정의 모두 사용 되 고 아무 곳에 나 기호가 사용 되었거나 호출을 확인 합니다.  
  
-   **함수를 사용 하지만 형식 또는 매개 변수 개수가 함수 정의와 일치 하지 않습니다.** 함수 선언은 정의와 일치해야 합니다. 함수 호출이 선언과 일치하며 선언이 정의와 일치하는지 확인하세요. 또한 템플릿 함수를 호출하는 코드에는 정의와 같은 템플릿 매개 변수가 포함되는 일치하는 템플릿 함수 선언이 있어야 합니다. 템플릿 선언은 불일치의 예를 들어 LNK2019e.cpp 예제 단원에서 샘플을 참조 합니다.  
  
-   **함수 또는 변수가 선언 되었지만 정의 되지 않았습니다.** 이 경우 대체로 한 선언이 헤더 파일에 존재 하지만 일치 하는 정의가 없는 구현 됩니다. 멤버 함수 또는 정적 데이터 멤버의 경우 구현에 클래스 범위 선택기가 포함되어야 합니다. 예를 들어 참조 [누락 함수 본문 또는 변수](../../error-messages/tool-errors/missing-function-body-or-variable.md)합니다.  
  
-   **호출 규칙 함수 선언 자와 함수 정의 간에 차이가 있습니다.** 호출 규칙 ([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md), 또는 [__vectorcall](../../cpp/vectorcall.md))은 데코레이팅된 이름의 일부로 인코딩됩니다. 호출 규칙이 동일한지 확인하세요.  
  
-   **기호가 C 파일에 정의 되어 있지만 c + + 파일에서 extern "C"를 사용 하지 않고 선언 됩니다.** C로 컴파일된 파일에 정의 된 기호는 사용 하지 않는 한 c + + 파일에 선언 된 기호와 다른 데코레이팅된 이름이 [extern "C"](../../cpp/using-extern-to-specify-linkage.md) 한정자입니다. 선언이 각 기호의 컴파일 링크와 일치하는지 확인하세요.  
  
     마찬가지로, C 프로그램에서 사용할 기호를 C++ 파일에서 정의하는 경우 정의에 `extern "C"` 을 사용하세요.  
  
-   **기호는 정적으로 정의 되 고 후 나중에 파일 외부 참조입니다.** C + +, C와 달리 [전역 상수](../../error-messages/tool-errors/global-constants-in-cpp.md) 가 `static` 링크 합니다. 이 제한을 해결하기 위해 헤더 파일에 `const` 초기화를 포함하고 .cpp 파일에 해당 헤더를 포함하거나, 변수를 비상수로 만들고 상수 참조를 사용하여 액세스할 수 있습니다.  
  
-   **클래스의 정적 멤버를 정의 되지 않았습니다.** 정적 클래스 멤버에는 고유한 정의가 있어야 합니다. 그렇지 않으면 단일 정의 규칙을 위반하게 됩니다. 인라인으로 정의될 수 없는 정적 클래스 멤버는 정규화된 이름을 사용하여 한 소스 파일에 정의되어야 합니다. 전혀 정의되지 않은 경우 링커는 LNK2019를 생성합니다.  
  
-   **빌드 종속성은 솔루션의 프로젝트 종속성 으로만 정의 합니다.** 이전 버전의 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]에서는 이 수준의 종속성으로 충분했습니다. 그러나 Visual Studio 2010부터 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 필요는 [프로젝트 간 참조](/visualstudio/ide/managing-references-in-a-project)합니다. 프로젝트에 프로젝트 간 참조가 없는 경우 이 링커 오류가 발생할 수 있습니다. 프로젝트 간 참조를 추가하여 오류를 해결하세요.  
  
-   **Windows 응용 프로그램에 대한 설정을 사용하여 콘솔 응용 프로그램을 빌드합니다**. 오류 메시지는 비슷한 경우 **WinMain 함수에서 참조 하는 확인 되지 않은 외부 기호**`function_name`, 링크를 사용 하 여 **/subsystem: console** 대신 **/SUBSYSTEM:WINDOWS**합니다. 이 설정에 대 한 자세한 내용은 Visual Studio에서이 속성을 설정 하는 방법에 대 한 지침은 참조 하십시오 [/SUBSYSTEM (하위 시스템 지정)](../../build/reference/subsystem-specify-subsystem.md)합니다.  
  
-   **다른 소스 파일에서 지정 된 함수 인라이닝에 대해 서로 다른 컴파일러 옵션을 사용 합니다.** 여러 소스 파일에서 .cpp 파일에 정의된 인라인된 함수를 사용하고 함수 인라이닝 컴파일러 옵션을 혼합하면 LNK2019가 발생할 수 있습니다. 자세한 내용은 참조 [함수 인라이닝 문제](../../error-messages/tool-errors/function-inlining-problems.md)합니다.  
  
-   **범위 밖의 자동 변수를 사용 합니다.** 자동(함수 범위) 변수는 해당 함수의 범위 내에서만 사용할 수 있습니다. 이러한 변수는 `extern` 으로 선언할 수 없으며 다른 소스 파일에서 사용할 수 없습니다. 예를 들어 참조 [자동 (함수 범위) 변수](../../error-messages/tool-errors/automatic-function-scope-variables.md)합니다.  
  
-   **내장 함수를 호출 하거나 대상 아키텍처에서 지원 되지 않는 내장 함수에 인수 형식을 전달 합니다.** 예를 들어 AVX2 내장 함수를 사용 하지만 지정 하지 않는 경우는 [/arch: avx2](../../build/reference/arch-x86.md) 컴파일러 옵션을 컴파일러는 내장 함수가 외부 함수 임을 가정 합니다. 인라인 명령을 생성하는 대신 컴파일러는 내장 함수와 같은 이름의 외부 기호에 대해 호출을 생성합니다. 링커가 이 누락된 함수의 정의를 찾으려고 할 때 LNK2019가 생성됩니다. 대상 아키텍처에서 지원하는 내장 함수 및 형식만 사용하는지 확인하세요.  
  
-   **하지 않는 코드와 네이티브 wchar_t를 사용 하는 코드를 혼합 합니다.** Visual C++ 2005에서 수행된 C++ 언어 규칙 작업은 `wchar_t` 를 기본적으로 네이티브 형식으로 만듭니다. 사용 해야는 [/Zc:wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 컴파일러 옵션을 이전 버전의 Visual c + +를 사용 하 여 컴파일된 개체 파일과 라이브러리와 호환 되는 코드를 생성 합니다. 일부 파일이 동일한 **/Zc:wchar_t** 설정을 사용하여 컴파일되지 않은 경우, 형식 참조가 호환되는 형식으로 확인되지 않을 수 있습니다. 사용된 형식을 업데이트하거나 컴파일할 때 일관된 `wchar_t` 설정을 사용하여 모든 라이브러리 및 개체 파일의 **/Zc:wchar_t** 형식이 호환되는지 확인하세요.  
  
 LNK2019의 원인 및 해결책에 대한 자세한 내용은 스택 오버플로 질문 [정의되지 않은 참조/확인되지 않은 외부 기호 오류란 무엇이며 어떻게 해결하나요?](http://stackoverflow.com/q/12573816/2002113)를 참조하세요.  
  
 **진단 도구**  
  
 링커가 특정 기호 정의를 찾을 수 없는 이유는 확인하기 어려울 수 있습니다. 빌드에 코드를 포함하지 않았거나, 빌드 옵션에서 외부 기호에 대해 다른 트데코레이된 이름을 생성한 경우가 종종 있습니다. LNK2019 오류를 진단하는데 도움이 되는 여러 가지 도구 및 옵션이 있습니다.  
  
-   [/verbose](../../build/reference/verbose-print-progress-messages.md) 링커 옵션은 링커가 참조는 파일을 확인 하는데 도움이 수 있습니다. 기호 정의를 포함하는 파일이 빌드에 포함되어 있는지 여부를 확인할 수 있습니다.  
  
-   [/EXPORTS](../../build/reference/dash-exports.md) 및 [/기호](../../build/reference/symbols.md) DUMPBIN 유틸리티의 옵션을 찾는 데 유용.dll 및 개체 또는 라이브러리 파일에는 기호가 정의 됩니다. 내보낸 트데코레이된 이름이 링커가 검색하는 트데코레이된 이름과 일치하는지 확인하세요.  
  
-   UNDNAME 유틸리티는 트데코레이된 이름에 해당하는 데코레이팅되지 않은 외부 기호를 보여 줄 수 있습니다.  
  
 **예제**  
  
 LNK2019 오류를 해결하는 방법에 대한 정보와 함께, LNK2019 오류를 유발하는 여러 가지 코드 예제는 다음과 같습니다.  
  
 **기호가 선언 되었지만 정의 되지 않았습니다.**  
  
 다음 샘플은 외부 기호가 선언되었지만 정의되지 않았기 때문에 LNK2019를 생성합니다.  
  
```cpp  
// LNK2019.cpp  
// Compile by using: cl /EHsc LNK2019.cpp  
// LNK2019 expected  
extern char B[100];   // B is not available to the linker  
int main() {  
   B[0] = ' ';   // LNK2019  
}  
```  
  
 또는 다음과 같은 예도 있습니다.  
  
```cpp  
// LNK2019c.cpp  
// Compile by using: cl /EHsc LNK2019c.cpp  
// LNK2019 expected  
extern int i;  
extern void g();  
void f() {  
   i++;  
   g();  
}  
int main() {}  
```  
  
 `i` 및 `g` 가 빌드의 파일 중 하나에 정의되지 않은 경우 링커는 LNK2019를 생성합니다. 컴파일의 일부로써 정의를 포함하는 소스 코드 파일을 포함하여 오류를 해결할 수 있습니다. 또는 정의를 포함하는 링커.obj 파일이나 .lib 파일에 전달할 수 있습니다.  
  
 **정적 데이터 멤버가 선언 되었지만 정의 되지 않았습니다.**  
  
 정적 데이터 멤버가 선언되었지만 정의되지 않은 경우에도 LNK2019가 발생할 수 있습니다. 다음 샘플에서는 LNK2019가 생성되며 해결 방법을 보여 줍니다.  
  
```cpp  
// LNK2019b.cpp  
// Compile by using: cl /EHsc LNK2019b.cpp  
// LNK2019 expected  
struct C {  
   static int s;  
};  
  
// Uncomment the following line to fix the error.  
// int C::s;  
  
int main() {  
   C c;  
   C::s = 1;  
}  
```  
  
 **선언 매개 변수가 정의와 일치 하지 않습니다.**  
  
 템플릿 함수를 호출하는 코드에는 일치하는 템플릿 함수 선언이 있어야 합니다. 선언에는 정의와 동일한 템플릿 매개 변수가 포함되어야 합니다. 다음 샘플에서는 사용자 정의 연산자에 LNK2019가 생성되고 해결 방법을 보여 줍니다.  
  
```cpp  
// LNK2019e.cpp  
// compile by using: cl /EHsc LNK2019e.cpp  
// LNK2019 expected  
#include <iostream>  
using namespace std;  
  
template<class T> class   
Test {  
   // The operator<< declaration does not match the definition below:  
   friend ostream& operator<<(ostream&, Test&);  
   // To fix, replace the line above with the following:  
   // template<typename T> friend ostream& operator<<(ostream&, Test<T>&);  
};  
  
template<typename T>  
ostream& operator<<(ostream& os, Test<T>& tt) {  
   return os;  
}  
  
int main() {  
   Test<int> t;  
   cout << "Test: " << t << endl;   // LNK2019 unresolved external  
}  
```  
  
 **일관성 없는 wchar_t 형식 정의**  
  
 다음 샘플에서는 `WCHAR`로 확인되는, `wchar_t`을 사용하는 내보내기가 있는 DLL이 생성됩니다.  
  
```cpp  
// LNK2019g.cpp  
// compile with: cl /EHsc /LD LNK2019g.cpp  
#include "windows.h"  
// WCHAR resolves to wchar_t  
__declspec(dllexport) void func(WCHAR*) {}  
```  
  
 다음 샘플은 이전 샘플에서 DLL을 사용 하 고 형식을 unsigned short * 및 WCHAR 때문에 l n k&2019;를 생성\* 같지는 않습니다.  
  
```cpp  
// LNK2019h.cpp  
// compile by using: cl /EHsc LNK2019h LNK2019g.lib  
// LNK2019 expected  
__declspec(dllimport) void func(unsigned short*);  
  
int main() {  
   func(0);  
}  
```  
  
 이 오류를 해결 하려면 변경 `unsigned short` 를 `wchar_t` 또는 `WCHAR`를 사용 하 여 LNK2019g.cpp를 컴파일 **/Zc:wchar_t-**합니다.
