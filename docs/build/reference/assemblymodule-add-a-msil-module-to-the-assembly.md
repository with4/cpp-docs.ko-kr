---
title: "/ASSEMBLYMODULE(MSIL 모듈을 어셈블리에 추가) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/assemblymodule"
  - "VC.Project.VCLinkerTool.AddModuleNamesToAssembly"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYMODULE 링커 옵션"
  - "어셈블리[C++]"
  - "어셈블리[C++], 모듈 추가"
  - "ASSEMBLYMODULE 링커 옵션"
  - "-ASSEMBLYMODULE 링커 옵션"
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYMODULE(MSIL 모듈을 어셈블리에 추가)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYMODULE:filename  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 이 어셈블리에 포함시킬 모듈입니다.  
  
## 설명  
 \/ASSEMBLYMODULE 옵션을 사용하면 어셈블리에 모듈 참조를 추가할 수 있습니다.  모듈 참조를 추가한 어셈블리 프로그램에서는 모듈의 형식 정보를 사용할 수 없습니다.  하지만 해당 어셈블리를 참조하는 모든 프로그램에서 모듈의 형식 정보를 사용할 수 있습니다.  
  
 모듈 참조를 어셈블리에 추가하고 이 모듈의 형식 정보를 어셈블리 프로그램에서 사용할 수 있도록 하려면 [\#using](../../preprocessor/hash-using-directive-cpp.md)을 사용합니다.  
  
 예를 들어, 다음 시나리오를 확인해 보십시오.  
  
1.  [\/LN](../../build/reference/ln-create-msil-module.md)을 사용하여 모듈을 만듭니다.  
  
2.  다른 프로젝트에 \/ASSEMBLYMODULE을 사용하여, 어셈블리를 만드는 현재 컴파일에 해당 모듈을 포함시킵니다.  이 프로젝트에서는 `#using`을 사용하여 모듈을 참조하지 않습니다.  
  
3.  또한 이 어셈블리를 참조하는 모든 프로젝트에서는 해당 모듈의 형식을 사용할 수 있습니다.  
  
 다음은 어셈블리 생성에 사용하는 기타 링커 옵션입니다.  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Visual C\+\+ 링커 입력으로.netmodule 파일을 수락 하 고 어셈블리 또는.netmodule를 링커에 입력 된 중에 런타임에 종속 하지를 사용 하 여.netmodule 링커에 의해 생성 된 출력 파일 수 있습니다.  자세한 내용은 [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **입력** 속성 페이지를 클릭합니다.  
  
4.  **어셈블리에 모듈 추가** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)