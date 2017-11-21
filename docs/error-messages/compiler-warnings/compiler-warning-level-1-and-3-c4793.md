---
title: "컴파일러 경고 (수준 1 및 3) C4793 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4793
dev_langs: C++
helpviewer_keywords:
- C6634
- C6635
- C6640
- C6630
- C6639
- C6636
- C6638
- C6631
- C6637
- C4793
ms.assetid: 819ada53-1d9c-49b8-a629-baf8c12314e6
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f2c133848adf634935287589c09b94ed871c93f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-and-3-c4793"></a>컴파일러 경고(수준 1 및 3) C4793
'function': 함수가 네이티브 코드로 컴파일 되었습니다. 'reason'  
  
 컴파일러가 컴파일할 수 없습니다 *함수* 관리 코드로는 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 지정 합니다. 대신, 컴파일러에서는 경고 C4793과 설명 메시지를 생성 하 고 컴파일할 수 있게 *함수* 네이티브 코드로 합니다. 연속 작업 메시지에 포함 되어는 *이유* 이유를 설명 하는 텍스트 *함수* 로 컴파일할 수 없는 `MSIL`합니다.  
  
 이 지정 하는 경우 수준 1 경고는 `/clr:pure` 컴파일러 옵션입니다.  **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않습니다.  
  
 다음 표에서 가능한 모든 후속 메시지를 나열합니다.  
  
|이유 메시지|설명|  
|--------------------|-------------|  
|정렬 된 데이터 형식은 관리 코드에서 지원 되지 않습니다.|CLR에서는 수 있어야 필요에 따라 데이터를 할당할 수 있는 하지 못할 수도 있습니다는 데이터와 같은 선언을 사용 하 여 정렬 된 경우 [__m128](../../cpp/m128.md) 또는 [맞춤](../../cpp/align-cpp.md)합니다.|  
|관리 코드에서 '__ImageBase'를 사용 하는 함수를 사용할 수 없습니다.|`__ImageBase`일반적으로 DLL을 로드 하는 하위 수준 네이티브 코드 에서만 사용 되는 특별 한 링커 기호가입니다.|  
|varargs에서 지원 되지 않는 ' / clr' 컴파일러 옵션|네이티브 함수에는 관리 되는 함수를 호출할 수 없습니다 [가변 인수 목록을 얻으려면](../../cpp/functions-with-variable-argument-lists-cpp.md) (varargs) 함수에 다른 스택을 레이아웃 요구 사항 때문에 있습니다. 그러나 지정 하는 경우는 `/clr:pure` 컴파일러 옵션을 가변 인수 목록은 어셈블리에 함수를 관리 되는 작업만 포함 될 수 있으므로 지원 됩니다. 자세한 내용은 참조 [순수형 및 안정형 코드 (C + + /cli CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.|  
|64 비트 CLR __ptr32 한정자로 선언 된 데이터를 지원 하지 않습니다.|포인터 크기가 현재 플랫폼에서 네이티브 포인터와 동일 해야 합니다. 자세한 내용은 참조 [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md)합니다.|  
|32 비트 CLR __ptr64 한정자로 선언 된 데이터를 지원 하지 않습니다.|포인터 크기가 현재 플랫폼에서 네이티브 포인터와 동일 해야 합니다. 자세한 내용은 참조 [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md)합니다.|  
|관리 코드에서 하나 이상의 내장 함수를 사용할 수 없습니다.|기본 이름을 메시지가 생성 되는 시간에 사용할 수 없으면입니다. 그러나 하위 수준 컴퓨터 명령을 일반적으로이 메시지를 발생 시키는 내장 나타냅니다.|  
|관리 코드에서는 인라인 네이티브 어셈블리 ('__asm')를 사용할 수 없습니다.|[인라인 어셈블리 코드](../../assembler/inline/asm.md) 는 관리할 수 없는 임의의 네이티브 코드가 포함 될 수 있습니다.|  
|__Clrcall이 아닌 가상 함수 썽크는 네이티브로 컴파일해야 합니다.|비-[__clrcall](../../cpp/clrcall.md) 가상 함수 썽크는 관리 되지 않는 주소를 사용 해야 합니다.|  
|'_Setjmp'를 사용 하는 함수는 네이티브로 컴파일해야 합니다.|CLR은 프로그램 실행을 제어할 수 있어야 합니다. 그러나는 [setjmp](../../cpp/using-setjmp-longjmp.md) 함수는 저장 및 레지스터 및 실행 상태와 같은 하위 수준 정보를 복원 하 여 일반적인 프로그램 실행을 건너뜁니다.|  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4793 합니다.  
  
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
  
```Output  
warning C4793: 'asmfunc' : function is compiled as native code:  
        Inline native assembly ('__asm') is not supported in managed code  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4793 합니다.  
  
```  
// C4793_b.cpp  
// compile with: /c /clr /W3  
#include <setjmp.h>  
jmp_buf test_buf;  
  
void f() {  
   setjmp(test_buf);   // C4793 warning  
}  
```  
  
```Output  
warning C4793: 'f' : function is compiled as native code:  
        A function using '_setjmp' must be compiled as native  
```