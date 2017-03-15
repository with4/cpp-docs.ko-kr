---
title: "GetProjectPath | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetProjectPath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProjectPath 메서드"
ms.assetid: a5e51fe4-c068-47b7-9f2f-1a1d6c71a963
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# GetProjectPath
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로젝트의 디렉터리 경로를 반환합니다.  
  
## 구문  
  
```  
  
      function GetProjectPath(   
   oProj    
);  
```  
  
#### 매개 변수  
 `oProj`  
 선택한 프로젝트입니다.  
  
## 반환 값  
 프로젝트의 디렉터리 경로입니다.  
  
## 설명  
 프로젝트의 경로를 구하려면 이 함수를 호출합니다.  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [GetProjectFile](../ide/getprojectfile.md)