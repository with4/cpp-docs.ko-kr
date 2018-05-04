---
title: -KEYCONTAINER (어셈블리에 서명할 키 컨테이너 지정) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
dev_langs:
- C++
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13058978b0833a17abbbfb68a2ed753aacfb6d49
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER(어셈블리에 서명할 키 컨테이너 지정)
```  
/KEYCONTAINER:name  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *name*  
 키가 포함 된 컨테이너입니다. 큰따옴표로 묶인 문자열 배치 ("")에 공백이 있는 경우.  
  
## <a name="remarks"></a>설명  
 링커를 어셈블리 매니페스트에 공개 키를 삽입 하 고 개인 키와 함께 최종 어셈블리에 서명 하 여 서명 된 어셈블리를 만듭니다. 키 파일을 생성 하려면 입력 [sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* 명령줄에서. **sn-i** 키 쌍이 컨테이너에 설치 합니다.  
  
 사용 하 여 컴파일하면 [/LN](../../build/reference/ln-create-msil-module.md), 키 파일의 이름이 모듈에 저장 되 고 어셈블리를 통해을 모듈에 대 한 명시적 참조를 포함 하는 어셈블리를 컴파일할 때 만들어진 [#using](../../preprocessor/hash-using-directive-cpp.md), 링크할 때 또는 [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)합니다.  
  
 컴파일러에 암호화 정보를 전달할 수도 [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)합니다. 사용 하 여 [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) 부분적으로 서명 된 어셈블리에 들어 있습니다. 참조 [강력한 이름 어셈블리 (어셈블리 서명) (C + + /cli CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) 어셈블리 서명에 대 한 자세한 내용은 합니다.  
  
 어셈블리 생성에 영향을 주는 다른 링커 옵션은:  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  에 옵션을 입력에서 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)