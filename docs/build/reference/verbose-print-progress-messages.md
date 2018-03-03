---
title: "-VERBOSE (인쇄 진행 메시지) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /verbose
- VC.Project.VCLinkerTool.ShowProgress
dev_langs:
- C++
helpviewer_keywords:
- -VERBOSE linker option
- linking [C++], session progress information
- Print Progress Messages linker option
- linker [C++], output dependency information
- /VERBOSE linker option
- dependencies [C++], dependency information in linker output
- VERBOSE linker option
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76ead441a8dc7ec65a6966371b83d42c47c897c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE(진행 메시지 표시)
```  
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]  
```  
  
## <a name="remarks"></a>설명  
 링커 전송 하는 링크 세션의 진행률에 대 한 정보는 **출력** 창. 명령줄에서 정보는 표준 출력으로 전송 되 고 파일로 리디렉션할 수 있습니다.  
  
|옵션|설명|  
|------------|-----------------|  
|/VERBOSE|연결 과정에 대 한 세부 정보를 표시 합니다.|  
|/VERBOSE: ICF|사용 하 여에서 발생 하는 링커 작업에 대 한 정보를 표시 [/opt: icf](../../build/reference/opt-optimizations.md)합니다.|  
|/VERBOSE: INCR|증분적인 링크 프로세스에 대한 정보를 표시합니다.|  
|/VERBOSE: LIB|검색된 라이브러리만 나타내는 진행률 메시지를 표시합니다.<br /><br /> 표시 된 정보 라이브러리 검색 프로세스가 포함 되며 각 라이브러리 및 개체 이름 목록 (전체 경로), 기호 확인 되는 라이브러리 및 기호를 참조 하는 개체의 목록에서 합니다.|  
|/VERBOSE: REF|사용 하 여에서 발생 하는 링커 작업에 대 한 정보를 표시 [/opt: ref](../../build/reference/opt-optimizations.md)합니다.|  
|/VERBOSE: SAFESEH|때 안전한 예외 처리와 호환 되지 않는 모듈에 대 한 정보를 표시 [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md) 지정 되지 않았습니다.|  
|/VERBOSE:UNUSEDLIBS|이미지를 만들 때 사용되지 않은 모든 라이브러리 파일에 대한 정보를 표시합니다.|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **링커** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  옵션을 추가 하는 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)