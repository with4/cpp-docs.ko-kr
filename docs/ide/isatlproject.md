---
title: "IsATLProject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IsATLProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsATLProject 메서드"
ms.assetid: 811115af-5bcd-4ce2-a514-34de4c7419ea
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# IsATLProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로젝트가 ATL 기반인지를 나타냅니다.  
  
## 구문  
  
```  
  
      function IsATLProject(   
   oProj    
);  
```  
  
#### 매개 변수  
 `oProj`  
 선택한 프로젝트입니다.  
  
## 반환 값  
 프로젝트가 ATL 프로젝트이면 **true**이고 그렇지 않으면 **false**입니다.  
  
## 설명  
 프로젝트가 ATL 기반인지를 나타냅니다.  
  
## 예제  
  
```  
function CanAddATLSupport(selProj, selObj)  
{  
   if (IsATLProject(selProj))  
   {  
      var L_ErrMsg1_Text = "Current project already has ATL support.";  
      wizard.ReportError(L_ErrMsg1_Text);  
      return false;  
   }  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [IsAttributedProject](../ide/isattributedproject.md)