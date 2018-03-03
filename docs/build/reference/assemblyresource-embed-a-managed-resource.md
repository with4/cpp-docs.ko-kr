---
title: "-ASSEMBLYRESOURCE (관리 되는 리소스 포함) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.EmbedManagedResourceFile
- /ASSEMBLYRESOURCE
dev_langs:
- C++
helpviewer_keywords:
- ASSEMBLYRESOURCE linker option
- assemblies [C++]
- -ASSEMBLYRESOURCE linker option
- assemblies [C++], linking resource files
- /ASSEMBLYRESOURCE linker option
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed8fd2b127a828eb8279671817cc4f099ae528c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="assemblyresource-embed-a-managed-resource"></a>/ASSEMBLYRESOURCE(관리되는 리소스 포함)
```  
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]  
```  
  
## <a name="parameters"></a>매개 변수  
 *filename*  
 이 어셈블리에 포함할 관리 되는 리소스입니다.  
  
 *name*  
 선택 사항입니다. 리소스에 대 한 논리적 이름 리소스를 로드 하는 데 사용 하는 이름입니다. 기본값은 파일 이름입니다.  
  
 필요에 따라 파일이 어셈블리 매니페스트에 개인 되어 있어야 하는 경우 지정할 수 있습니다. 기본적으로 *이름* 어셈블리에 공개 합니다.  
  
## <a name="remarks"></a>설명  
 하지만 옵션을 사용 하 여 어셈블리에 리소스를 포함 하려면.  
  
 리소스는 링커를 사용 하 여 만든 어셈블리에서 공용입니다. 링커가는 어셈블리에 리소스의 이름을 바꿀 수 없습니다.  
  
 경우 *filename* .NET Framework 리소스 (.resources) 만들어진 파일, 예를 들어 여는 [리소스 파일 생성기 (Resgen.exe)](/dotnet/framework/tools/resgen-exe-resource-file-generator) 개발 환경에서의 멤버와 액세스할 수 있습니다 또는 **System.Resources** 네임 스페이스 (참조 [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx) 자세한 정보에 대 한). 다른 모든 리소스는 **런타임에** \* 메서드 **System.Reflection.Assembly** 런타임 시 리소스에 액세스 하는 클래스입니다.  
  
 어셈블리 생성에 영향을 주는 다른 링커 옵션은:  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **입력** 속성 페이지.  
  
4.  수정 된 **관리 되는 리소스 파일 포함** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)