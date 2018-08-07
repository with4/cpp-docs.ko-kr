---
title: -Gh (_penter 후크 함수 사용) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _penter
dev_langs:
- C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68497e4e760e1268a0175d5a68452678153896b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373155"
---
# <a name="gh-enable-penter-hook-function"></a>/Gh(_penter 후크 함수 사용)
에 대 한 호출으로 인해는 `_penter` 모든 메서드 또는 함수의 시작 부분에 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Gh  
```  
  
## <a name="remarks"></a>설명  
 `_penter` 함수 라이브러리의 일부가 아니며에 대 한 정의에 `_penter`합니다.  
  
 명시적으로 호출 하려는 경우가 아니면 `_penter`, 프로토타입을 제공 필요가 없습니다. 함수 처럼 다음과 같은 프로토타입을 이전의 하 고 항목에 모든 레지스터의 내용을 강제 종료 시 변경 되지 않은 콘텐츠를 팝에 나타나야 합니다.  
  
```  
void __declspec(naked) _cdecl _penter( void );  
```  
  
 이 선언은 64 비트 프로젝트에 대 한 공간이 없습니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="example"></a>예제  
 로 컴파일하는 경우 다음 코드 **/Gh**, 표시 방법을 `_penter` 두 번 호출 됩니다 함수를 입력할 때 한 번 `main` 함수를 입력할 때 한 번 `x`합니다.  
  
```  
// Gh_compiler_option.cpp  
// compile with: /Gh  
// processor: x86  
#include <stdio.h>  
void x() {}  
  
int main() {  
   x();  
}  
  
extern "C" void __declspec(naked) _cdecl _penter( void ) {  
   _asm {  
      push eax  
      push ebx  
      push ecx  
      push edx  
      push ebp  
      push edi  
      push esi  
    }  
  
   printf_s("\nIn a function!");  
  
   _asm {  
      pop esi  
      pop edi  
      pop ebp  
      pop edx  
      pop ecx  
      pop ebx  
      pop eax  
      ret  
    }  
}  
```  
  
```Output  
In a function!  
In a function!  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)