---
title: "-Os-Ot (크기 우선 코드, 속도 우선 코드) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
dev_langs:
- C++
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02ce4b7d5c9617a88450fd90b4ac6c75d41148ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /OT(크기 우선 코드, 속도 우선 코드)
최소화 또는 Exe 및 Dll의 크기를 최대화 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Os  
/Ot  
```  
  
## <a name="remarks"></a>설명  
 **/Os** (크기 우선 코드) 컴파일러에 속도 보다 크기를 우선 하도록 지시 하 여 Exe 및 Dll의 크기를 최소화 합니다. 컴파일러 많은 C 및 c + + 구문을 기능이 비슷한 기계어 코드 시퀀스를 축소할 수 있습니다. 경우에 따라 이러한 차이 크기와 속도의 균형을 제공합니다. **/Os** 및 **/Ot** 옵션 각각에 대해 한 기본 설정을 지정할 수 있습니다.  
  
 **/Ot** (우선 코드 속도) 컴파일러에 크기 보다 속도 우선 하도록 지시 하 여 Exe 및 Dll의 속도 최대화 합니다. (기본값입니다.) 컴파일러 많은 C 및 c + + 구문을 기능이 비슷한 기계어 코드 시퀀스를 축소할 수 있습니다. 경우에 따라서는 이러한 차이 크기와 속도의 균형을 제공합니다. 속도 최대화 /Ot 옵션도 포함 됩니다 ([/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)) 옵션입니다. **/O2** 옵션 매우 빠르게 코드를 생성 하는 몇 가지 옵션을 결합 합니다.  
  
 사용 하는 경우 **/Os** 또는 **/Ot**를 지정 해야 합니다 [/Og](../../build/reference/og-global-optimizations.md) 는 코드를 최적화 합니다.  
  
> [!NOTE]
>  프로 파일링 테스트 실행에서 수집 되는 정보는 될 수 있는 효과에 지정 하는 경우 최적화를 재정의 합니다 **/Ob**, **/Os**, 또는 **/Ot**합니다. 자세한 내용은 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)합니다.  
  
 **x86 특정**  
  
 다음 코드 예제에서는 코드 크기 우선 차이점을 보여 줍니다 (**/Os**) 옵션 및 속도 우선 코드 (**/Ot**) 옵션:  
  
> [!NOTE]
>  다음 사용 하는 경우 예상 되는 동작에 설명 **/Os** 또는 **/Ot**합니다. 그러나 컴파일러 동작 릴리스 간 아래 코드에 대 한 서로 다른 최적화 될 수 있습니다.  
  
```  
/* differ.c  
  This program implements a multiplication operator  
  Compile with /Os to implement multiply explicitly as multiply.  
  Compile with /Ot to implement as a series of shift and LEA instructions.  
*/  
int differ(int x)  
{  
    return x * 71;  
}  
```  
  
 아래 기계어 코드 조각에 나와 있는 것 처럼 DIFFER.c를 컴파일할 때 크기에 대 한 (**/Os**), 컴파일러 구현 하는 곱하기 return 문의 식으로 명시적으로 한 코드의 짧지만 느린 시퀀스:  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
imul   eax, 71                  ; 00000047H  
```  
  
 DIFFER.c를 속도 대해 컴파일할 때에 또는 (**/Ot**), 컴파일러 구현 하는 곱하기를 일련의 전환이 return 문의 식 및 `LEA` 빠르지만 긴 시퀀스의 코드를 생성 하는 지침은:  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
mov    ecx, eax  
shl    eax, 3  
lea    eax, DWORD PTR [eax+eax*8]  
sub    eax, ecx  
```  
  
 **최종 x86 특정**  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **최적화** 속성 페이지.  
  
4.  수정 된 **크기 또는 속도** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [/O 옵션 (코드 최적화)](../../build/reference/o-options-optimize-code.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)