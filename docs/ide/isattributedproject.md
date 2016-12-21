---
title: "IsAttributedProject | Microsoft Docs"
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
  - "IsAttributedProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsAttributedProject 메서드"
ms.assetid: 8fe41c0c-40e7-42be-8e15-94a2bbbe87cc
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IsAttributedProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로젝트에서 특성을 사용하는지를 나타냅니다.  
  
## 구문  
  
```  
  
      function IsAttributedProject(   
   owizard    
);  
```  
  
#### 매개 변수  
 *owizard*  
 마법사 개체입니다.  
  
## 반환 값  
 프로젝트에서 특성을 사용하면 **true**이고 그렇지 않으면 **false**입니다.  
  
## 설명  
 프로젝트에서 특성을 사용하는지를 나타냅니다.  
  
## 예제  
  
```  
function CheckAddtoProject(oProj)  
{  
   try  
   {  
      if (!IsAttributedProject(wizard))  
      {  
         if (!ConvertProjectToAttributed(oProj))  
            return false;  
       }  
   }  
   catch (e)  
   {  
      var L_ErrMsg1_Text = "Error in CheckAddtoProject: ";  
         wizard.ReportError( L_ErrMsg1_Text + e.description);  
         return false;  
   }  
  
   return true;  
}  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [IsATLProject](../ide/isatlproject.md)   
 [IsMFCProject](../ide/ismfcproject.md)