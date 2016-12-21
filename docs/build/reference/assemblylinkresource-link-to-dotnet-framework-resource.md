---
title: "/ASSEMBLYLINKRESOURCE(.NET Framework 리소스에 대한 링크) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/ASSEMBLYLINKRESOURCE"
  - "VC.Project.VCLinkerTool.AssemblyLinkResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYLINKRESOURCE 링커 옵션"
  - "ASSEMBLYLINKRESOURCE 링커 옵션"
  - "-ASSEMBLYLINKRESOURCE 링커 옵션"
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYLINKRESOURCE(.NET Framework 리소스에 대한 링크)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYLINKRESOURCE:filename  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 어셈블리에서 링크할 .NET Framework 리소스 파일입니다.  
  
## 설명  
 \/ASSEMBLYLINKRESOURCE 옵션은 출력 파일에 .NET Framework 리소스에 대한 링크를 만듭니다. 리소스 파일은 출력 파일에 저장되지 않습니다.  출력 파일에 리소스 파일을 포함하려면 [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) 옵션을 사용합니다.  
  
 링커를 사용하여 만든 어셈블리에서는 링크된 리소스가 공용입니다.  
  
 \/ASSEMBLYLINKRESOURCE를 사용하려면 컴파일할 때 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) 옵션을 사용해야 합니다. [\/LN](../../build/reference/ln-create-msil-module.md)이나 [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)는 \/ASSEMBLYLINKRESOURCE와 함께 사용할 수 없습니다.  
  
 *filename*이 [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md)를 사용하여 만들었거나 개발 환경에서 만든 .NET Framework 리소스 파일이면 **System.Resources** 네임스페이스의 멤버를 사용하여 해당 파일에 액세스할 수 있습니다.  자세한 내용은 [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx)를 참조하십시오.  다른 모든 리소스의 경우에는 런타임에 **System.Reflection.Assembly** 클래스의 **GetManifestResource**\* 메서드를 사용하여 리소스에 액세스합니다.  
  
 *filename*에는 모든 파일 형식이 가능합니다.  예를 들어, 어셈블리의 네이티브 dll 부분을 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있도록 만들 수 있습니다.  
  
 다음은 어셈블리 생성에 사용하는 기타 링커 옵션입니다.  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)