---
title: "컴파일러 경고(수준 1 및 3) C4793 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4793"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4793"
  - "C6630"
  - "C6631"
  - "C6634"
  - "C6635"
  - "C6636"
  - "C6637"
  - "C6638"
  - "C6639"
  - "C6640"
ms.assetid: 819ada53-1d9c-49b8-a629-baf8c12314e6
caps.latest.revision: 28
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1 및 3) C4793
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수가 네이티브로 컴파일되었습니다. 'reason'  
  
 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션이 지정되어 있더라도 컴파일러에서 *function*을 관리 코드로 컴파일할 수 없습니다.  대신 컴파일러에서는 경고 C4793과 후속 설명 메시지를 생성한 다음 *function*을 네이티브 코드로 컴파일합니다.  후속 메시지에는 *function*가 `MSIL`로 컴파일할 수 없는 이유를 설명하는 *reason* 텍스트가 들어 있습니다.  
  
 이 경고는 `/clr:pure` 컴파일러 옵션을 지정할 경우 수준 1 경고입니다.  
  
 다음 표에서는 가능한 모든 후속 메시지를 보여 줍니다.  
  
|원인 메시지|설명|  
|------------|--------|  
|관리 코드에서는 정렬된 데이터 형식이 지원되지 않습니다.|CLR에서는 필요에 따라 데이터를 할당할 수 있어야 하는데 데이터가 [\_\_m128](../../cpp/m128.md) 또는 [align](../../cpp/align-cpp.md)와 같은 선언을 사용하여 정렬된 경우에는 이것이 가능하지 않을 수 있습니다.|  
|관리 코드에서는 '\_\_ImageBase'를 사용하는 함수를 사용할 수 없습니다.|`__ImageBase`는 일반적으로 하위 수준 네이티브 코드에서만 DLL을 로드하는 데 사용되는 특수 링커 기호입니다.|  
|'\/clr' 컴파일러 옵션을 지정하면 varargs를 사용할 수 없습니다.|[가변 인수 목록](../../misc/variable-argument-lists.md)\(varargs\)이 있는 관리되는 함수는 네이티브 함수와 스택 레이아웃 요구 사항이 다르므로 네이티브 함수에서 이러한 함수를 호출할 수 없습니다.  그러나 `/clr:pure` 컴파일러 옵션을 지정할 경우에는 어셈블리에 관리되는 함수만 포함할 수 있으므로 가변 인수 목록을 사용할 수 있습니다.  자세한 내용은 [순수형 및 안정형 코드](../../dotnet/pure-and-verifiable-code-cpp-cli.md)을 참조하십시오.|  
|64비트 CLR은 \_\_ptr32 한정자로 선언된 데이터를 지원하지 않습니다.|포인터는 현재 플랫폼의 네이티브 포인터와 동일한 크기여야 합니다.  자세한 내용은 [\_\_ptr32, \_\_ptr64](../../cpp/ptr32-ptr64.md)을 참조하십시오.|  
|32비트 CLR은 \_\_ptr64 한정자로 선언된 데이터를 지원하지 않습니다.|포인터는 현재 플랫폼의 네이티브 포인터와 동일한 크기여야 합니다.  자세한 내용은 [\_\_ptr32, \_\_ptr64](../../cpp/ptr32-ptr64.md)을 참조하십시오.|  
|관리 코드에서는 하나 이상의 내장 함수를 사용할 수 없습니다.|메시지가 생성되는 시점에서는 내장 함수 이름을 사용할 수 없습니다.  그러나 이 메시지를 발생시킨 내장 함수는 일반적으로 하위 수준의 기계어 명령을 나타냅니다.|  
|관리 코드에서는 인라인 네이티브 어셈블리\('\_\_asm'\)를 사용할 수 없습니다.|[인라인 어셈블리 코드](../../assembler/inline/asm.md)에는 관리할 수 없는 임의의 네이티브 코드가 포함될 수 있습니다.|  
|\_\_clrcall이 아닌 가상 함수 썽크는 네이티브로 컴파일해야 합니다.|[\_\_clrcall](../../cpp/clrcall.md)이 아닌 가상 함수 썽크에서는 관리되지 않는 주소를 사용해야 합니다.|  
|'\_setjmp'를 사용하는 함수는 네이티브로 컴파일해야 합니다.|CLR에서는 프로그램 실행을 제어할 수 있어야 합니다.  그러나 [setjmp](../../cpp/using-setjmp-longjmp.md) 함수는 레지스터 및 실행 상태와 같은 하위 수준의 정보를 저장 및 복원하여 일반적인 프로그램 실행을 건너뜁니다.|  
  
## 예제  
 다음 샘플에서는 C4793 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4793.cpp  
// compile with: /c /clr /W3   
// processor: x86  
int asmfunc(void) {   // C4793, compiled as unmanaged, native code  
   __asm {  
      mov eax, 0  
   }  
}  
```  
  
  **경고 C4793: 'asmfunc' 함수가 네이티브 코드로 컴파일되었습니다.**  
 **관리 코드에서는 인라인 네이티브 어셈블리\('\_\_asm'\)를 사용할 수 없습니다.**   
## 예제  
 다음 샘플에서는 C4793 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4793_b.cpp  
// compile with: /c /clr /W3  
#include <setjmp.h>  
jmp_buf test_buf;  
  
void f() {  
   setjmp(test_buf);   // C4793 warning  
}  
```  
  
  **경고 C4793: 함수가 네이티브 코드로 컴파일되었습니다.**  
 **'\_setjmp'를 사용하는 함수는 네이티브로 컴파일해야 합니다.**