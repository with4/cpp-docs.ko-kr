---
title: "/Zc:inline(참조되지 않은 COMDAT 제거) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:inline"
  - "VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc 컴파일러 옵션(C++)"
  - "/Zc:inline"
  - "Zc 컴파일러 옵션(C++)"
  - "-Zc 컴파일러 옵션(C++)"
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /Zc:inline(참조되지 않은 COMDAT 제거)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

COMDAT이거나 내부 링크만 있는 참조되지 않은 함수 또는 데이터를 제거합니다.  **\/Zc:inline**을 지정한 경우 컴파일러를 사용하려면 인라인 데이터 또는 인라인 함수를 사용하는 변환 단위에 해당 데이터 및 함수에 대한 정의도 포함되어 있어야 합니다.  
  
## 구문  
  
```  
/Zc:inline[-]  
```  
  
## 설명  
 **\/Zc:inline**을 지정한 경우 컴파일러는 참조되지 않은 COMDAT 함수 또는 데이터나 내부 링크만 있는 함수 또는 데이터에 대한 기호 정보를 내보내지 않습니다.  이 옵션은 기본적으로 해제되어 있습니다\(**\/Zc:inline\-**\).  이러한 최적화는 릴리스 빌드에서 또는 링커 옵션 [\/OPT:REF](../../build/reference/opt-optimizations.md)가 지정된 경우 링커가 수행하는 일부 작업을 간소화합니다.  컴파일러가 이러한 최적화를 수행하면 .obj f파일의 크기를 크게 줄이고 링커 속도를 상당히 높일 수 있습니다.  최적화를 사용하지 않거나\([\/Od](../../build/reference/od-disable-debug.md)\) [\/GL\(전체 프로그램 최적화\)](../../build/reference/gl-whole-program-optimization.md)을 지정한 경우 이 컴파일러 옵션을 사용하지 않습니다.  
  
 **\/Zc:inline**을 지정한 경우 컴파일러는 `inline`을 선언한 모든 함수에는 동일한 변환 단위에서 사용할 수 있는 정의가 있어야 한다는 C\+\+11 요구 사항을 강제합니다.  이 옵션을 지정하지 않으면 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]에서는 표시되는 정의가 없더라도 `inline`을 선언한 함수를 호출하는 비호환 코드를 허용합니다.  자세한 내용은 섹션 3.2 및 7.1.2에서 C\+\+11 표준을 참조하세요.  이 컴파일러 옵션은 Visual Studio 2013 업데이트 2에서 정의되었습니다.  
  
 **\/Zc:inline** 옵션을 사용하려면 호환되지 않는 코드를 업데이트합니다.  다음 예제에서는 기본 **\/Zc:inline\-** 옵션이 사용되는 경우 정의 없이 인라인 함수 선언의 호환되지 않는 사용이 컴파일되어 연결되는 방법을 보여줍니다.  
  
```cpp  
// example.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#pragma once  
  
class Example {  
public:  
   inline void inline_call(); // declared but not defined inline  
   void normal_call();  
   Example() {};  
};  
```  
  
```cpp  
// example.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include <stdio.h>  
#include "example.h"  
  
void Example::inline_call() {  
   printf("inline_call was called.\n");   
}  
  
void Example::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file  
}  
```  
  
```cpp  
// zcinline.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include "example.h"  
  
void main() {  
   Example example;  
   example.inline_call(); // normal call when definition unavailable  
}  
```  
  
 **\/Zc:inline**을 사용하도록 설정하면 컴파일러가 example.obj의 `Example::inline_call`에 대한 인라인되지 않은 코드 본문을 내보내지 않으므로 동일한 코드가 [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) 오류를 발생하게 합니다.  따라서 `main`에서 인라인되지 않은 호출이 발생해 정의되지 않은 외부 기호를 참조하게 됩니다.  
  
 이러한 오류를 해결하기 위해 `Example::inline_call` 선언에서 `inline` 키워드를 제거하거나 `Example::inline_call`의 정의를 헤더 파일로 이동하거나 `Example`의 구현을 main.cpp로 이동할 수 있습니다.  다음 예제에서는 헤더를 포함한 모든 호출자에게 정의가 표시되는 헤더 파일로 정의를 이동합니다.  
  
```cpp  
// example2.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#pragma once  
#include <stdio.h>  
  
class Example2 {  
public:  
   inline void inline_call() {  
      printf("inline_call was called.\n");   
   }  
   void normal_call();  
   Example2() {};  
};  
```  
  
```cpp  
// example2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void Example2::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call();   
}  
```  
  
```cpp  
// zcinline2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void main() {  
   Example2 example2;  
   example2.inline_call(); // normal call when definition unavailable  
}  
```  
  
 Visual C\+\+의 규칙과 관련된 문제에 대한 자세한 내용은 [비표준 동작](../../cpp/nonstandard-behavior.md)을 참조하세요.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  `/Zc:inline`을 포함하도록 **추가 옵션** 속성을 수정한 다음 **확인**을 선택합니다.  
  
## 참고 항목  
 [\/Zc\(규칙\)](../../build/reference/zc-conformance.md)