---
title: "/VERSION(버전 정보) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.Version"
  - "/version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/VERSION 링커 옵션"
  - "버전 정보 링커 옵션"
  - "VERSION 링커 옵션"
  - "-VERSION 링커 옵션"
  - "버전 번호, .exe에서 지정"
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /VERSION(버전 정보)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/VERSION:major[.minor]  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *major* 및 *minor*  
 .exe 또는 .dll 파일의 헤더에 지정할 버전 번호입니다.  
  
## 설명  
 \/VERSION 옵션을 사용하면 링커에서는 .exe 또는 .dll 파일의 헤더에 버전 번호를 포함합니다.  DUMPBIN [\/HEADERS](../../build/reference/headers.md)를 사용하면 OPTIONAL HEADER VALUES의 이미지 버전 필드를 표시하여 \/VERSION의 결과를 확인할 수 있습니다.  
  
 *major* 및 *minor* 인수는 0에서 65,535까지의 10진수로서,  기본값은 버전 0.0입니다.  
  
 \/VERSION으로 지정한 정보는 파일 Windows 탐색기에서 등록 정보를 표시할 때 나타나는 응용 프로그램의 버전 번호와는 관계 없습니다.  이 버전 정보는 응용 프로그램을 빌드할 때 사용되는 리소스 파일에서 가져온 것입니다.  자세한 정보는 [버전 정보 편집기](../../mfc/version-information-editor.md)를 참조하십시오.  
  
 버전 번호를 삽입하는 다른 방법은 [VERSION](../../build/reference/version-c-cpp.md) 모듈 정의 문을 사용하는 것입니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **일반** 속성 페이지를 클릭합니다.  
  
4.  **버전** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)