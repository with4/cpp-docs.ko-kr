---
title: "/TLBID(TypeLib의 리소스 ID 지정) | Microsoft Docs"
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
  - "/tlbid"
  - "VC.Project.VCLinkerTool.TypeLibraryResourceID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".tlb 파일, 리소스 ID 지정"
  - "/TLBID 링커 옵션"
  - "tlb 파일, 리소스 ID 지정"
  - "TLBID 링커 옵션"
  - "-TLBID 링커 옵션"
  - "형식 라이브러리, 리소스 ID 지정"
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /TLBID(TypeLib의 리소스 ID 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TLBID:id  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `id`  
 링커에서 만든 형식 라이브러리의 사용자 지정 값입니다.  기본 리소스 ID인 1 대신 사용됩니다.  
  
## 설명  
 특성을 사용하는 프로그램을 컴파일할 때 링커에서는 형식 라이브러리를 만들고,  이 형식 라이브러리에 리소스 ID 1을 할당합니다.  
  
 이 리소스 ID가 기존 리소스 ID 중 하나와 충돌하면 \/TLBID를 사용하여 다른 ID를 지정할 수 있습니다.  `id`로 전달할 수 있는 값은 1에서 65535까지입니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **포함 IDL** 속성 페이지를 클릭합니다.  
  
4.  **TypeLib 리소스 ID** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)