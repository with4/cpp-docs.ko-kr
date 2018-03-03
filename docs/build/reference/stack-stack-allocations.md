---
title: "-STACK (스택 할당) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.StackReserveSize
- VC.Project.VCLinkerTool.StackCommitSize
- /stack
dev_langs:
- C++
helpviewer_keywords:
- STACK linker option
- -STACK linker option
- memory allocation, stack
- /STACK linker option
- stack, setting size
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6b487ff830abd3dfa97a748c81d541cbd9fdd0b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stack-stack-allocations"></a>/STACK(스택 할당)
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>설명  
 /STACK 옵션 바이트의 스택 크기를 설정합니다. .Exe 파일을 작성 하는 경우에이 옵션을 사용 합니다.  
  
 `reserve` 가상 메모리에서 총 스택 할당을 지정 하는 값입니다. ARM, x86 및 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴퓨터의 경우 기본 스택 크기는 1MB입니다.  
  
 `commit`운영 체제에 의해 해석 될 수 있습니다. Windows WindowsRT에서는 한 번에 할당할 실제 메모리의 양을 지정합니다. 커밋된 가상 메모리 공간을 예약 하는 페이징 파일에서 발생 합니다. 응용 프로그램에 더 많은 스택 공간이 필요할 때 `commit` 값이 크면 시간을 줄일 수 있지만 메모리 요구 사항이 늘어나고 시작 시간이 오래 걸릴 수 있습니다. ARM, x86 및 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴퓨터의 경우 기본 커밋 값은 4KB입니다.  
  
 10진수 또는 C 언어 표기법으로 `reserve` 및 `commit` 값을 지정합니다.  
  
 또 다른 방법은 스택 크기를 설정 하는 [STACKSIZE](../../build/reference/stacksize.md) 모듈 정의 (.def) 파일의 문입니다. **STACKSIZE** 스택 할당을 재정의 합니다. (/stack) 모두 지정 된 옵션입니다. .Exe 파일을 사용 하 여 빌드한 후에 스택 크기를 변경할 수는 [EDITBIN](../../build/reference/editbin-reference.md) 도구입니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **링커** 폴더입니다.  
  
3.  선택 된 **시스템** 속성 페이지.  
  
4.  다음 속성 중 하나를 수정 합니다.  
  
    -   **스택 커밋 크기**  
  
    -   **스택 예약 크기**  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A> 속성을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)