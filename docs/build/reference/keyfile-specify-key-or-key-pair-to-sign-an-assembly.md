---
title: -KEYFILE (어셈블리에 서명할 키 또는 키 쌍 지정) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /keyfile
- VC.Project.VCLinkerTool.KeyFile
dev_langs:
- C++
helpviewer_keywords:
- /KEYFILE linker option
- -KEYFILE linker option
- KEYFILE linker option
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 476fd1e49a8c93363f00215d422a79eda808c321
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378823"
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE(어셈블리에 서명할 키 또는 키 쌍 지정)
```  
/KEYFILE:filename  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 키가 포함 된 파일입니다. 큰따옴표로 묶인 문자열 배치 ("")에 공백이 있는 경우.  
  
## <a name="remarks"></a>설명  
 링커는 공개 키를 어셈블리 매니페스트에 삽입 한 다음 개인 키와 함께 최종 어셈블리에 서명 합니다. 키 파일을 생성 하려면 입력 [sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* 명령줄에서. 서명 된 어셈블리에 강력한 이름이 라고 합니다.  
  
 사용 하 여 컴파일하면 [/LN](../../build/reference/ln-create-msil-module.md), 키 파일의 이름이 모듈에 저장 되 고 어셈블리를 통해을 모듈에 대 한 명시적 참조를 포함 하는 어셈블리를 컴파일할 때 만들어진 [#using](../../preprocessor/hash-using-directive-cpp.md), 링크할 때 또는 [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)합니다.  
  
 사용 하 여 링커가 암호화 정보를 전달할 수도 [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)합니다. 사용 하 여 [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) 부분적으로 서명 된 어셈블리에 들어 있습니다. 참조 [강력한 이름 어셈블리 (어셈블리 서명) (C + + /cli CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) 어셈블리 서명에 대 한 자세한 내용은 합니다.  
  
 둘 다 경우 **/KEYFILE** 및 **/KEYCONTAINER** ´ ï ´ (명령줄 옵션이 나 사용자 지정 특성), 링커는 먼저 키 컨테이너를 시도 합니다. 키 컨테이너를 찾으면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다. 키 컨테이너를 찾지 못하면 링커 경우 /KEYFILE로 지정 된 파일을 시도 합니다. 해당 파일을 찾으면 키 파일의 정보를 사용하여 어셈블리가 서명되고, 키 정보가 키 컨테이너에 설치되므로(sn -i와 유사) 다음에 컴파일할 때 키 컨테이너가 유효해집니다.  
  
 키 파일에는 공개 키만 포함될 수 있습니다.  
  
 참조 [and using strong-named Assemblies](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies) 어셈블리 서명에 대 한 자세한 내용은 합니다.  
  
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