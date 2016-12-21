---
title: "/ASSEMBLYRESOURCE(관리되는 리소스 포함) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.EmbedManagedResourceFile"
  - "/ASSEMBLYRESOURCE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYRESOURCE 링커 옵션"
  - "어셈블리[C++]"
  - "어셈블리[C++], 리소스 파일 링크"
  - "ASSEMBLYRESOURCE 링커 옵션"
  - "-ASSEMBLYRESOURCE 링커 옵션"
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYRESOURCE(관리되는 리소스 포함)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]  
```  
  
## 매개 변수  
 *filename*  
 이 어셈블리에 포함시킬 관리되는 리소스입니다.  
  
 *name*  
 선택적 요소로서,  리소스의 논리적 이름, 즉 리소스를 로드하는 데 사용되는 이름입니다.  기본값은 파일 이름입니다.  
  
 어셈블리 매니페스트에서 파일이 private인지 여부를 지정할 수도 있습니다.  기본적으로 *name*은 어셈블리에서 public 파일입니다.  
  
## 설명  
 어셈블리에 리소스를 포함시키려면 \/ASSEMBLYRESOURCE 옵션을 사용합니다.  
  
 링커를 사용하여 만든 어셈블리에서는 리소스가 공용입니다.  링커에서는 어셈블리의 리소스 이름을 바꿀 수 없습니다.  
  
 *filename*이 [리소스 파일 생성기\(Resgen.exe\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md)를 사용하여 만들었거나 개발 환경에서 만든 .NET Framework 리소스 파일\(.resources\)이면 **System.Resources** 네임스페이스의 멤버를 사용하여 해당 파일에 액세스할 수 있습니다. 자세한 내용은 [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx)를 참조하십시오.  다른 모든 리소스의 경우에는 런타임에 **System.Reflection.Assembly** 클래스의 **GetManifestResource**\* 메서드를 사용하여 리소스에 액세스합니다.  
  
 다음은 어셈블리 생성에 사용하는 기타 링커 옵션입니다.  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **입력** 속성 페이지를 클릭합니다.  
  
4.  **관리되는 리소스 파일 포함** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)