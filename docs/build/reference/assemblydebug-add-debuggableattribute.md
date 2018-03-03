---
title: "-ASSEMBLYDEBUG (DebuggableAttribute 추가) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.AssemblyDebug
- /ASSEMBLYDEBUG
dev_langs:
- C++
helpviewer_keywords:
- /ASSEMBLYDEBUG linker option
- -ASSEMBLYDEBUG linker option
- ASSEMBLYDEBUG linker option
ms.assetid: 94443af3-470c-41d7-83a0-7434563d7982
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80b4759b5594096b3a599d6e3324bfeaab0376a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="assemblydebug-add-debuggableattribute"></a>/ASSEMBLYDEBUG(DebuggableAttribute 추가)
```  
/ASSEMBLYDEBUG[:DISABLE]  
```  
  
 /ASSEMBLYDEBUG 내보내는 **DebuggableAttribute** 디버그 정보 추적은 사용 하 고 JIT 최적화를 사용 하 여 특성입니다. 원본에는 다음 특성이 지정과 같습니다.  
  
```  
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG  
```  
  
 /Assemblydebug: disable 내보내는 **DebuggableAttribute** 특성 디버그 정보 추적을 해제 하지만 JIT 최적화를 활성화 합니다. 원본에는 다음 특성이 지정과 같습니다.  
  
```  
[assembly:Debuggable(false, false)];   // same as /ASSEMBLYDEBUG:DISABLE  
```  
  
 기본값은 출력 하지는 **DebuggableAttribute** 특성입니다.  
  
 DebuggableAttribute 소스 코드에서 직접 어셈블리에 추가할 수도 있습니다. 예를 들어 개체에 적용된  
  
```  
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG  
```  
  
## <a name="remarks"></a>설명  
 명시적으로 관리 되는 이미지를 디버깅할 수를 지정 하는 데 필요한 경우 사용 하 여 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) 만으로는 충분 하지 않습니다.  
  
 어셈블리 생성에 영향을 주는 다른 링커 옵션은:  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **디버그** 속성 페이지.  
  
4.  수정 된 **디버깅 가능한 어셈블리** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AssemblyDebug%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)