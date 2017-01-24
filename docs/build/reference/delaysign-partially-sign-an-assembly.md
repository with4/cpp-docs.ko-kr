---
title: "/DELAYSIGN(어셈블리에 부분적으로 서명) | Microsoft Docs"
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
  - "/delaysign"
  - "VC.Project.VCLinkerTool.DelaySign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAYSIGN 링커 옵션"
  - "DELAYSIGN 링커 옵션"
  - "-DELAYSIGN 링커 옵션"
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DELAYSIGN(어셈블리에 부분적으로 서명)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAYSIGN[:NO]  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 NO  
 어셈블리가 부분적으로 서명되지 않도록 지정합니다.  
  
## 설명  
 어셈블리에 공개 키만 넣으려는 경우에는 **\/DELAYSIGN**을 사용하십시오.  기본값은 **\/DELAYSIGN:NO**입니다.  
  
 **\/DELAYSIGN** 옵션은 [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) 또는 [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)와 함께 사용해야만 적용됩니다.  
  
 완전히 서명된 어셈블리를 요청하면 컴파일러가 매니페스트\(어셈블리 메타데이터\)가 포함된 파일을 해시한 후 해당 해시를 개인 키로 서명합니다.  결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다.  어셈블리의 서명이 연기된 경우에는 링커에서 서명을 계산하여 저장하지 않지만 나중에 서명을 추가할 수 있도록 파일에 공간을 예약합니다.  
  
 예를 들어, **\/DELAYSIGN**을 사용하면 테스트하는 사람이 어셈블리를 전역 캐시에 넣을 수 있으며,  테스트를 마친 후 어셈블리에 개인 키를 넣으면 어셈블리에 완전히 서명할 수 있습니다.  
  
 어셈블리에 서명하는 데 대한 자세한 내용은 [강력한 이름 어셈블리\(어셈블리 서명\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) 및 [어셈블리 서명 연기](../Topic/Delay%20Signing%20an%20Assembly.md)를 참조하십시오.  
  
 다음은 어셈블리 생성에 사용하는 기타 링커 옵션입니다.  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
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