---
title: -MIDL (MIDL 명령줄 옵션 지정) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
dev_langs:
- C++
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d125042041af1e20b6dfc4a02197c2124adbeb9a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375190"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL(MIDL 명령줄 옵션 지정)
```  
/MIDL:@file  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `file`  
 포함 하는 파일의 이름 [MIDL 명령줄 옵션](http://msdn.microsoft.com/library/windows/desktop/aa366839)합니다.  
  
## <a name="remarks"></a>설명  
 IDL 파일을 TLB 파일로 변환에 대 한 모든 옵션을 지정 해야 `file`; MIDL 명령줄 옵션을 링커의 명령줄에서 지정할 수 없습니다. /MIDL 지정 되지 않은 경우 MIDL 컴파일러 IDL 파일 이름 및 기타 옵션 없이 호출 됩니다.  
  
 파일 줄당 하나의 MIDL 명령줄 옵션을 포함 해야 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **포함 IDL** 속성 페이지.  
  
4.  수정 된 **MIDL 명령** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [/IDLOUT (MIDL 출력 파일 이름)](../../build/reference/idlout-name-midl-output-files.md)   
 [/IGNOREIDL (특성 처리을 MIDL로)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/TLBOUT (이름입니다. TLB 파일)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [특성을 사용하는 프로그램 빌드](../../windows/building-an-attributed-program.md)