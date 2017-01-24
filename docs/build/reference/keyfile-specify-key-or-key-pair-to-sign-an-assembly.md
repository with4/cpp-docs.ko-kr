---
title: "/KEYFILE(어셈블리에 서명할 키 또는 키 쌍 지정) | Microsoft Docs"
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
  - "/keyfile"
  - "VC.Project.VCLinkerTool.KeyFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/KEYFILE 링커 옵션"
  - "KEYFILE 링커 옵션"
  - "-KEYFILE 링커 옵션"
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /KEYFILE(어셈블리에 서명할 키 또는 키 쌍 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/KEYFILE:filename  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 키를 가지고 있는 파일입니다.  공백이 있으면 문자열을 큰따옴표\(" "\)로 묶습니다.  
  
## 설명  
 링커에서는 어셈블리 매니페스트에 공개 키를 삽입하고 최종 어셈블리에 개인 키로 서명합니다.  키 파일을 생성하려면 명령줄에 [sn \-k](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) `file`을 입력하십시오.  서명된 어셈블리는 강력한 이름을 갖는다고 합니다.  
  
 [\/LN](../../build/reference/ln-create-msil-module.md)을 사용하여 컴파일하면 키 파일의 이름이 모듈에 저장됩니다. 그런 다음 [\#using](../../preprocessor/hash-using-directive-cpp.md)을 통해 이 모듈에 대한 명시적 참조가 포함된 어셈블리를 컴파일하거나 [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)을 사용하여 링크하면 이때 만들어지는 어셈블리에 키 파일이 통합됩니다.  
  
 [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)를 사용하여 링커에 암호화 정보를 전달할 수도 있습니다.  어셈블리에 부분적으로 서명하려는 경우에는 [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)을 사용하십시오.  어셈블리에 서명하는 데 대한 자세한 내용은 [강력한 이름 어셈블리\(어셈블리 서명\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)를 참조하십시오.  
  
 명령줄 옵션 또는 사용자 지정 특성으로 **\/KEYFILE**과 **\/KEYCONTAINER**를 둘 다 지정한 경우 링커에서는 먼저 키 컨테이너를 사용하려고 합니다.  키 컨테이너에서 성공하면 어셈블리는 키 컨테이너의 정보로 서명됩니다.  링커에서 키 컨테이너를 찾지 못할 경우에는 \/KEYFILE로 지정된 파일을 사용하려고 합니다.  키 파일에서 성공하면 어셈블리는 키 파일의 정보로 서명되며 다음에 컴파일할 때 키 컨테이너를 사용할 수 있도록 키 정보가 키 컨테이너에 설치됩니다\(sn \-i와 유사\).  
  
 키 파일에는 공개 키만 포함될 수 있습니다.  
  
 어셈블리 서명에 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)을 참조하십시오.  
  
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