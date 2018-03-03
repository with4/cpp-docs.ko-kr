---
title: "-ASSEMBLYLINKRESOURCE (.NET Framework 리소스에 대 한 링크) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
dev_langs:
- C++
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6a5ab1211cf3a1d5c834c0d32f1840db1bc2bf1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE(.NET Framework 리소스에 대한 링크)
```  
/ASSEMBLYLINKRESOURCE:filename  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 어셈블리에서 연결할 .NET Framework 리소스 파일입니다.  
  
## <a name="remarks"></a>설명  
 /ASSEMBLYLINKRESOURCE 옵션은 출력 파일에.NET Framework 리소스에 대 한 링크를 만듭니다. 리소스 파일 출력 파일에 배치 되지 않습니다. [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) 출력 파일에 리소스 파일을 포함 합니다.  
  
 연결 된 리소스는 링커를 사용 하 여 만든 어셈블리에서 공용입니다.  
  
 /ASSEMBLYLINKRESOURCE 컴파일을 포함 해야 [/clr](../../build/reference/clr-common-language-runtime-compilation.md); [/LN](../../build/reference/ln-create-msil-module.md) 또는 [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) /ASSEMBLYLINKRESOURCE 허용 되지 않습니다.  
  
 경우 *filename* .NET Framework 리소스 파일인, 예를 들어에서 만든 [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) 개발 환경에서의 멤버와 액세스할 수 있습니다 또는 **System.Resources** 네임 스페이스입니다. 자세한 내용은 참조 [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx)합니다. 다른 모든 리소스를 사용 하 여는 **런타임에** \* 의 메서드는 **System.Reflection.Assembly** 런타임 시 리소스에 액세스 하는 클래스입니다.  
  
 *filename* 어떠한 파일 형식도 될 수 있습니다. 예를 들어 다음 전역 어셈블리 캐시에 설치 및 어셈블리에 관리 코드에서 액세스할 수 있도록 하는 어셈블리의 네이티브 DLL 부분을 확인 하는 것이 좋습니다.  
  
 어셈블리 생성에 영향을 주는 다른 링커 옵션은:  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
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