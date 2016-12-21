---
title: "/RTC(런타임 오류 검사) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/rtc"
  - "VC.Project.VCCLCompilerTool.SmallerTypeCheck"
  - "VC.Project.VCCLCompilerTool.UninitializedVariableCheck"
  - "VC.Project.VCCLCompilerTool.StackFrameCheck"
  - "VC.Project.VCCLCompilerTool.BasicRuntimeChecks"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RTC1 컴파일러 옵션[C++]"
  - "/RTCc 컴파일러 옵션[C++]"
  - "/RTCs 컴파일러 옵션[C++]"
  - "/RTCu 컴파일러 옵션[C++]"
  - "__MSVC_RUNTIME_CHECKS 매크로"
  - "RTC1 컴파일러 옵션"
  - "-RTC1 컴파일러 옵션[C++]"
  - "RTCc 컴파일러 옵션"
  - "-RTCc 컴파일러 옵션[C++]"
  - "RTCs 컴파일러 옵션"
  - "-RTCs 컴파일러 옵션[C++]"
  - "RTCu 컴파일러 옵션"
  - "-RTCu 컴파일러 옵션[C++]"
  - "런타임 검사, /RTC 옵션"
  - "런타임 오류, 오류 검사"
  - "런타임 오류, 런타임 검사"
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /RTC(런타임 오류 검사)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[runtime\_checks](../../preprocessor/runtime-checks.md) pragma와 함께 런타임 오류 검사 기능을 사용하거나 사용하지 않도록 설정하는 데 사용됩니다.  
  
## 구문  
  
```  
/RTC1  
/RTCc  
/RTCs  
/RTCu  
```  
  
## 인수  
 `1`  
 **\/RTC** `su`에 해당합니다.  
  
 `c`  
 더 작은 데이터 형식에 값이 할당됨으로써 데이터 손실이 발생하는 경우 이를 보고합니다.  `short 0x101` 형식의 값을 `char` 형식의 변수에 할당하는 경우를 예를 들 수 있습니다.  
  
 이 옵션을 사용하면 `int`의 처음 8비트를 필요로 할 때 그 결과가 `char`로서 반환되는 경우와 같이, 의도적으로 잘라내기를 한 경우에도 보고됩니다.  할당으로 인해 정보가 손실되는 경우 **\/RTC**`c`는 런타임 오류를 발생시키므로, 사용자는 **\/RTC**`c`의 결과로 발생하는 런타임 오류를 방지하기 위해 필요한 정보를 숨길 수 있습니다.  예를 들면 다음과 같습니다.  
  
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
 다음과 같이 스택 프레임 런타임 오류 검사를 수행합니다.  
  
-   지역 변수를 0이 아닌 값으로 초기화합니다.  이렇게 하면 디버그 모드에서 실행할 때 발견하지 못한 버그를 찾는 데 도움이 됩니다.  릴리스 빌드에서 스택 변수의 컴파일러 최적화 때문에, 릴리스 빌드보다 디버그 빌드에서 스택 변수가 0이 될 가능성이 더 높습니다.  일단 프로그램에서 해당 스택 영역이 사용되었으면, 컴파일러에 의해 0으로 다시 설정되지 않습니다.  따라서, 같은 스택 영역을 사용하는 초기화되지 않은 다음 스택 변수는 이 스택 메모리에서 이전에 사용한 값을 반환할 수 있습니다.  
  
-   배열 같은 로컬 변수의 오버런 및 언더런을 감지합니다.  **\/RTC**`s`는 구조 내에서 컴파일러 패딩으로 인한 메모리에 액세스할 때 오버런을 탐지하지 못합니다.  패딩은 [맞춤](../../cpp/align-cpp.md), [\/Zp\(구조체 멤버 맞춤\)](../../build/reference/zp-struct-member-alignment.md) 또는 [pack](../../preprocessor/pack.md)을 사용하거나, 컴파일러에 패딩 추가를 요청하는 것과 같은 방식으로 구조 요소를 주문하는 경우에 발생할 수 있습니다.  
  
-   스택 포인터 손상을 탐지하는 스택 포인터 확인을 수행합니다.  스택 포인터 손상은 호출 규칙 불일치에 의해 발생할 수 있습니다.  예를 들어, 함수 포인터를 사용하여 내보내지는 DLL의 함수가 [\_\_stdcall](../../cpp/stdcall.md)로 호출되지만, 함수에 대한 포인터는 [\_\_cdecl](../../cpp/cdecl.md)로 선언됩니다.  
  
 `u`  
 초기화되지 않은 변수를 사용할 경우 보고합니다.  예를 들어, `C4701`을 생성하는 명령에서도 **\/RTC**`u`를 사용하면 런타임 오류가 발생할 수 있습니다.  [컴파일러 경고\(수준 1 및 수준 4\) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)을 생성하는 모든 명령에서는 **\/RTC**`u`를 사용하면 런타임 오류가 발생합니다.  
  
 그러나 다음 코드 부분을 살펴보십시오.  
  
```  
int a, *b, c;  
if ( 1 )  
b = &a;  
c = a;  // No run-time error with /RTCu  
```  
  
 변수는 초기화될 수 있는 경우 **\/RTC**`u`에 의해 런타임에 보고되지 않습니다.  예를 들어, 변수의 별칭이 포인터를 통해 지정된 후에는 컴파일러에서 변수를 추적하지 않으며 초기화되지 않은 사용을 보고하지 않습니다.  실제로, 사용자는 주소를 통해 변수를 초기화할 수 있습니다.  & 연산자는 이 경우 할당 연산자 역할을 수행합니다.  
  
## 설명  
 런타임 오류 검사를 통해 실행 코드에서 문제를 발견할 수 있습니다. 자세한 내용은 [방법: 네이티브 런타임 검사 기능 사용](../Topic/How%20to:%20Use%20Native%20Run-Time%20Checks.md)을 참조하십시오.  
  
 **\/RTC** 컴파일러 옵션을 사용하여 명령줄에서 프로그램을 컴파일하는 경우, 코드의 모든 [최적화](../../preprocessor/optimize.md) pragma 명령은 실패합니다.  이는 런타임 오류 검사가 릴리스 최적화 빌드에서 유효하지 않기 때문입니다.  
  
 개발 빌드에는 **\/RTC**를 사용하고 **\/RTC**는 소매 빌드에는 사용해서는 안 됩니다.  **\/RTC**는 컴파일러 최적화에 사용할 수 없습니다 \([\/O 옵션\(코드 최적화\)](../../build/reference/o-options-optimize-code.md)\).  **\/RTC**를 사용하여 빌드한 프로그램 이미지는 **\/Od**를 사용하여 빌드한 이미지보다 약간 크고 속도가 약간 느립니다\(**\/Od** 빌드의 경우보다 5% 느림\).  
  
 \_\_MSVC\_RUNTIME\_CHECKS 전처리기 지시문은 사용자가 **\/RTC** 옵션이나 [\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)를 사용할 때 정의됩니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **코드 생성** 속성 페이지를 클릭합니다.  
  
4.  **기본 런타임 검사** 또는 **작은 형식 검사** 속성 중 하나 또는 양쪽 모두를 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A> 속성을 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [RTC sample](http://msdn.microsoft.com/ko-kr/b3415b09-f6fd-43dc-8c02-9a910bc2574e)