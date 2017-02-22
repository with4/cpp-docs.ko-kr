---
title: "/MANIFESTFILE(매니페스트 파일 이름 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ManifestFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTFILE 링커 옵션"
  - "MANIFESTFILE 링커 옵션"
  - "-MANIFESTFILE 링커 옵션"
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /MANIFESTFILE(매니페스트 파일 이름 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFESTFILE:filename  
```  
  
## 설명  
 \/MANIFESTFILE을 사용하면 매니페스트 파일의 기본 이름을 변경할 수 있습니다.  매니페스트 파일의 기본 이름은 파일 이름에 .manifest가 붙은 이름입니다.  
  
 [\/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)를 사용하여 링크하지 않으면 \/MANIFESTFILE이 적용되지 않습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **매니페스트 파일** 속성 페이지를 선택합니다.  
  
5.  **매니페스트 파일** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)