---
title: "DoesIncludeExist | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DoesIncludeExist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoesIncludeExist 메서드"
ms.assetid: 39751a3d-dfe5-423c-bd94-a53771c3e360
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# DoesIncludeExist
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정한 헤더 파일에 대한 `#include` 문이 파일에 있는지를 나타냅니다.  
  
## 구문  
  
```  
  
      function DoesIncludeExist(   
   oProj,   
   strHeaderFile,   
   strInsertIntoFile    
);  
```  
  
#### 매개 변수  
 `oProj`  
 선택한 프로젝트입니다.  
  
 *strHeaderFile*  
 찾을 헤더 파일의 이름입니다.  
  
 `strInsertIntoFile`  
 헤더 파일에 대한 `#include` 문이 들어 있는 소스 파일입니다.  
  
## 반환 값  
 지정한 헤더 파일이 있으면 **true**이고 그렇지 않으면 **false**입니다.  
  
## 설명  
 `strInsertIntoFile`로 지정한 파일에 특정 헤더 파일에 대한 \#include 문이 있는지를 나타냅니다.  
  
## 예제  
  
```  
// Check to see if #include for atlbase.h   
// is included in the project's stdafx.h.  
// and add it if it is not.  
if (!DoesIncludeExist(selProj, "<atlbase.h>", strSTDAFX))  
   oCM.AddInclude("<atlbase.h>", strSTDAFX, vsCMAddPositionEnd);  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)