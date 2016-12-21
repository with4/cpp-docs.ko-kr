---
title: "/NOASSEMBLY(MSIL 모듈 만들기) | Microsoft Docs"
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
  - "/NOASSEMBLY"
  - "VC.Project.VCLinkerTool.TurnOffAssemblyGeneration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NOASSEMBLY 링커 옵션"
  - "어셈블리[C++]"
  - "어셈블리[C++], 어셈블리를 만들지 않음"
  - "NOASSEMBLY 링커 옵션"
  - "-NOASSEMBLY 링커 옵션"
ms.assetid: 3cea4e70-f451-4395-a626-1930b1b127fe
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /NOASSEMBLY(MSIL 모듈 만들기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NOASSEMBLY  
```  
  
## 설명  
 \/NOASSEMBLY 옵션을 사용하면 .NET Framework 어셈블리 없이 현재 출력 파일에 대한 이미지를 만들도록 링커에 지시할 수 있습니다.  어셈블리 매니페스트가 없는 MSIL 출력 파일을 모듈이라고 합니다.  
  
 기본적으로는 어셈블리가 만들어집니다.  [\/LN\(MSIL 모듈 만들기\)](../../build/reference/ln-create-msil-module.md) 컴파일러 옵션을 사용하여 모듈을 만들 수도 있습니다.  
  
 다음은 어셈블리 생성에 사용하는 기타 링커 옵션입니다.  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **어셈블리 생성 안 함** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TurnOffAssemblyGeneration%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)