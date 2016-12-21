---
title: "Templates.inf 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "사용자 지정 마법사, 템플릿 파일"
ms.assetid: 93d60d27-2402-4dc8-a829-e97417ccea49
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Templates.inf 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Templates.inf는 프로젝트를 위해 렌더링할 템플릿의 목록이 들어 있는 텍스트 파일입니다.  
  
 Templates.inf는 자체가 [템플릿 파일](../ide/template-files.md)이기 때문에 사용자의 선택에 따라 프로젝트에 포함할 파일을 지시문에서 지정할 수 있습니다.  이 파일에서 사용할 수 있는 지시문의 목록은 [템플릿 지시문](../ide/template-directives.md)을 참조하십시오.  
  
## 예제  
  
```  
Template1.txt  
Template2.txt  
  [!if TYPE_A]  
TemplateOptionA.h  
TemplateOptionA.cpp  
  [!else]  
TemplateOptionB.h  
TemplateOptionB.cpp  
  [!endif]  
```  
  
 **CreateCustomInfFile**은 Templates.inf를 임시 텍스트 파일로 렌더링합니다. 해당 파일을 처리한 후에 이 임시 텍스트 파일은 삭제되어야 합니다.  
  
## 예제  
  
```  
var InfFile = CreateCustomInfFile();  
AddFilesToProject(selProj, strProjectName, InfFile);  
InfFile.Delete();  
```  
  
 자세한 내용은 [JScript 파일](../ide/jscript-file.md)을 참조하십시오.  
  
## 참고 항목  
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)