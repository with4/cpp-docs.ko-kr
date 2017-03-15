---
title: "/INCLUDE(강제 기호 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/include"
  - "VC.Project.VCLinkerTool.ForceSymbolReferences"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/INCLUDE 링커 옵션"
  - "강제 기호 참조 링커 옵션"
  - "INCLUDE 링커 옵션"
  - "-INCLUDE 링커 옵션"
  - "강제 기호 참조 링커"
  - "기호, 기호 테이블에 추가"
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /INCLUDE(강제 기호 참조)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/INCLUDE:symbol  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `symbol`  
 기호 테이블에 추가할 기호를 지정합니다.  
  
## 설명  
 \/INCLUDE 옵션을 사용하면 지정된 기호를 기호 테이블에 추가하도록 링커에 지시할 수 있습니다.  
  
 기호를 여러 개 지정하려면 기호 이름 사이에 쉼표\(,\), 세미콜론\(;\) 또는 공백을 입력합니다.  명령줄에서는 각 기호에 대해 \/INCLUDE:`symbol`을 한 번씩 지정합니다.  
  
 링커는 기호 정의가 포함되어 있는 개체를 프로그램에 추가하여 `symbol`을 확인합니다.  이 기능은 프로그램에 링크되지 않는 라이브러리 개체를 포함시킬 때 유용합니다.  
  
 이 옵션을 사용하여 기호를 지정하면 [\/OPT:REF](../../build/reference/opt-optimizations.md)에 의한 해당 기호의 제거는 무시됩니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **입력** 속성 페이지를 클릭합니다.  
  
4.  **강제 기호 참조** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)