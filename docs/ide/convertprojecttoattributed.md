---
title: "ConvertProjectToAttributed | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ConvertProjectToAttributed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ConvertProjectToAttributed 메서드"
ms.assetid: 56a2d6e1-7e8e-4595-b2be-ade026593798
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ConvertProjectToAttributed
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

특성을 사용하지 않는 ATL 프로젝트를 특성을 사용하도록 변환합니다.  
  
## 구문  
  
```  
  
function ConvertProjectToAttributed( );  
  
```  
  
## 반환 값  
 프로젝트가 변환되었으면 **true**이고 그렇지 않으면 **false**입니다.  
  
## 설명  
 특성을 사용하지 않는ATL 프로젝트를 특성을 사용하도록 변환하려면 이 함수를 호출합니다.  자세한 내용은 [특성을 사용하는 프로그래밍](../windows/attributed-programming-concepts.md)을 참조하십시오.  
  
## 예제  
  
```  
// Create a function called CheckAddtoProject.  
function CheckAddtoProject(oProj)  
{  
// Is the project attributed already?  
   try  
   {  
      if (!IsAttributedProject(wizard))  
      {  
         // If the project is not converted to attributed, return false.  
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
 [CanAddNonAttributed](../ide/canaddnonattributed.md)