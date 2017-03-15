---
title: "/ASSEMBLYDEBUG(DebuggableAttribute 추가) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.AssemblyDebug"
  - "/ASSEMBLYDEBUG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYDEBUG 링커 옵션"
  - "ASSEMBLYDEBUG 링커 옵션"
  - "-ASSEMBLYDEBUG 링커 옵션"
ms.assetid: 94443af3-470c-41d7-83a0-7434563d7982
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /ASSEMBLYDEBUG(DebuggableAttribute 추가)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYDEBUG[:DISABLE]  
```  
  
 \/ASSEMBLYDEBUG는 **DebuggableAttribute** 특성을 생성하고 디버그 정보 추적을 사용하며 JIT 최적화를 비활성화합니다.  이 옵션은 소스에서 다음 특성을 지정하는 것과 같습니다.  
  
```  
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG  
```  
  
 \/ASSEMBLYDEBUG:DISABLE은 **DebuggableAttribute** 특성을 생성하지만 디버그 정보 추적을 해제하고 JIT 최적화를 활성화합니다.  이 옵션은 소스에서 다음 특성을 지정하는 것과 같습니다.  
  
```  
[assembly:Debuggable(false, false)];   // same as /ASSEMBLYDEBUG:DISABLE  
```  
  
 기본 동작은 **DebuggableAttribute** 특성을 생성하지 않는 것입니다.  
  
 소스 코드에서 직접 DebuggableAttribute를 어셈블리에 추가할 수도 있습니다.  예를 들면 다음과 같습니다.  
  
```  
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG  
```  
  
## 설명  
 Visual C\+\+ .NET 2003 이후 버전에서는 관리되는 이미지의 디버깅 가능 여부를 명시적으로 지정해야 합니다.  [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)만 사용하는 것으로는 충분하지 않습니다.  
  
 다음은 어셈블리 생성에 사용하는 기타 링커 옵션입니다.  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **디버그** 속성 페이지를 클릭합니다.  
  
4.  **디버깅 가능한 어셈블리** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AssemblyDebug%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)