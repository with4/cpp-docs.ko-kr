---
title: -RTC (런타임 오류 검사) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /rtc
- VC.Project.VCCLCompilerTool.SmallerTypeCheck
- VC.Project.VCCLCompilerTool.UninitializedVariableCheck
- VC.Project.VCCLCompilerTool.StackFrameCheck
- VC.Project.VCCLCompilerTool.BasicRuntimeChecks
dev_langs:
- C++
helpviewer_keywords:
- /RTCs compiler option [C++]
- -RTC1 compiler option [C++]
- run-time errors, error checks
- -RTCu compiler option [C++]
- /RTC1 compiler option [C++]
- /RTCc compiler option [C++]
- /RTCu compiler option [C++]
- __MSVC_RUNTIME_CHECKS macro
- -RTCs compiler option [C++]
- RTCs compiler option
- RTC1 compiler option
- run-time errors, run-time checks
- run-time checks, /RTC option
- RTCu compiler option
- RTCc compiler option
- -RTCc compiler option [C++]
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a135c9c4e32ea7a54c45719eff503ff99509d3e7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378459"
---
# <a name="rtc-run-time-error-checks"></a>/RTC(런타임 오류 검사)
설정 및 런타임 오류 검사 기능을 함께에서 사용 하지 않도록 설정 하는 데 사용 된 [runtime_checks](../../preprocessor/runtime-checks.md) pragma입니다.  
  
## <a name="syntax"></a>구문  
  
```  
/RTC1  
/RTCc  
/RTCs  
/RTCu  
```  
  
## <a name="arguments"></a>인수  
 `1`  
 해당 **/RTC**`su`합니다.  
  
 `c`  
 보고서 값 보다 작은 데이터 형식 및 데이터 손실을 결과에 할당 됩니다. 예를 들어 형식의 값 `short 0x101` 형식의 변수에 할당 `char`합니다.  
  
 이 옵션을 사용할 파일을 자르거나 예를 들어의 처음 8 비트를 원하는 경우 경우 보고는 `int` 으로 반환 되는 `char`합니다. 때문에 **/RTC** `c` 하면 런타임 오류가 발생의 결과로 런타임 오류를 방지 하는 데 필요한 정보 가릴 수 정보를 할당으로 인해 분실 한 경우 **/RTC** `c`. 예를 들어:  
  
```  
#include <crtdbg.h>  
  
char get8bits(int value, int position) {  
   _ASSERT(position < 32);  
   return (char)(value >> position);  
   // Try the following line instead:  
   // return (char)((value >> position) & 0xff);  
}  
  
int main() {  
   get8bits(12341235,3);  
}  
```  
  
 `s`  
 스택 프레임 런타임 오류 검사, 다음과 같습니다.  
  
-   지역 변수는 0이 아닌 값으로 초기화 합니다. 이렇게 하면 디버그 모드에서 실행할 때 표시 되지 않는 버그를 식별 합니다. 수 있으므로 큰 스택 변수에 릴리스 빌드에서 스택 변수의 컴파일러 최적화 때문에 릴리스 빌드를 디버그 빌드에서 0 수 있습니다. 일단 프로그램에는 해당 스택 영역 사용 되었으면, 컴파일러에 의해 0으로 다시 설정 되지 않습니다. 따라서 동일한 스택 영역을 사용 하는 후속, 초기화 되지 않은 스택 변수에이 스택 메모리를 사용 하는 이전에서 남은 값을 반환할 수 있습니다.  
  
-   배열과 같은 지역 변수의 언더런 및 오버런 감지 합니다. **/RTC** `s` 컴파일러 패딩으로 구조체 내에서 결과 메모리에 액세스할 때 오버런을 감지 하지 못하고 있습니다. 안쪽 여백을 사용 하 여 발생할 수 [맞춤](../../cpp/align-cpp.md), [/Zp (구조체 멤버 맞춤)](../../build/reference/zp-struct-member-alignment.md), 또는 [팩](../../preprocessor/pack.md), 컴파일러에 안쪽 여백을 추가 하는 방식에 구조 요소를 주문 하는 경우 또는 합니다.  
  
-   스택 스택 포인터 손상 검색 하는 포인터 확인 합니다. 스택 포인터 손상 호출 규칙 불일치로 인해 발생할 수 있습니다. 예를 들어 함수 포인터를 사용 하 여 사용자 함수를 호출으로 내보낸 DLL에 [__stdcall](../../cpp/stdcall.md) 로 함수에 포인터를 선언 하지만 [__cdecl](../../cpp/cdecl.md)합니다.  
  
 `u`  
 초기화 되지 않은 변수를 사용 하면 보고 합니다. 예를 들어, 생성 하는 명령 `C4701` 에서 런타임 오류가 발생할 수도 있습니다 **/RTC**`u`합니다. 생성 하는 모든 명령 [컴파일러 경고 (수준 1 및 수준 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) 에서 런타임 오류가 생성 됩니다 **/RTC**`u`합니다.  
  
 그러나 다음 코드 조각을 고려 합니다.  
  
```cpp  
int a, *b, c;  
if ( 1 )  
b = &a;  
c = a;  // No run-time error with /RTCu  
```  
  
 변수는 초기화 될 수, 하는 경우 그 하 여 런타임 시 보고 되지 것입니다 **/RTC**`u`합니다. 예를 들어 변수는 포인터를 통해 별칭이 지정 되 면는 컴파일러에서 하지 변수를 추적 하 고 초기화 되지 않은 사용을 보고 합니다. 실제로 해당 주소를 수행 하 여 변수를 초기화할 수 있습니다. & 연산자는 이 경우에 할당 연산자와 같이 사용됩니다.  
  
## <a name="remarks"></a>설명  
 런타임 오류 검사는 실행 중인 코드의 문제를 찾을 수 있는 방법 자세한 내용은 참조 [하는 방법: 사용 하 여 네이티브 런타임 검사](/visualstudio/debugger/how-to-use-native-run-time-checks)합니다.  
  
 중 하나를 사용 하 여 명령줄에서 프로그램을 컴파일하는 경우는 **/RTC** 컴파일러 옵션, pragma [최적화](../../preprocessor/optimize.md) 코드의 지침에는 자동으로 실패 합니다. 런타임 오류 검사 (최적화) 릴리스 빌드에 유효 하지 않은 때문입니다.  
  
 사용 해야 **/RTC** 개발 빌드;에 대 한 **/RTC** 정품 빌드에 사용할 수 없습니다. **/RTC** 컴파일러 최적화 함께 사용할 수 없습니다 ([/O 옵션 (코드 최적화)](../../build/reference/o-options-optimize-code.md)). 프로그램 이미지를 사용 하 여 빌드한 **/RTC** 조금 더 큰 및 사용 하 여 빌드된 이미지 보다 조금 느리기 됩니다 **/Od** (5% 방식 보다 속도가 느립니다는 **/Od** 빌드).  
  
 사용할 때 __MSVC_RUNTIME_CHECKS 전처리기 지시문을 정의할 **/RTC** 옵션 또는 [/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **코드 생성** 속성 페이지.  
  
4.  다음 속성 중 하나 또는 모두를 수정: **기본 런타임 검사** 또는 **작은 형식 검사**합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A> 속성을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [방법: 네이티브 런타임 검사 기능 사용](/visualstudio/debugger/how-to-use-native-run-time-checks)