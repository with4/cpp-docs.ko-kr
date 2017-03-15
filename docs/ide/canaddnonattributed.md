---
title: "CanAddNonAttributed | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanAddNonAttributed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddNonAttributed 메서드"
ms.assetid: a2b0143e-f84b-40f3-8f51-23a492f651f8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanAddNonAttributed
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

특성을 사용하지 않는 개체를 ATL 프로젝트에서 지원하는지를 확인합니다.  
  
## 구문  
  
```  
  
function CanAddNonAttributed( );  
  
```  
  
## 반환 값  
 프로젝트에서 특성을 사용하는 ATL 개체와 특성을 사용하지 않는 개체를 모두 지원하면 **true**이고 특성을 사용하는 프로젝트만 지원하면 **false**입니다.  
  
## 설명  
 프로젝트에서 특성을 사용하는 개체와 특성을 사용하지 않는 개체를 모두 지원하는지를 확인하려면 이 함수를 호출합니다.  
  
## 예제  
  
```  
// Check if attributed project using CanAddNonAttributed  
window.external.Load(document);  
if (IsAttributedProject(window.external))  
{  
   ATTRIBUTED.checked = true;  
   if (!CanAddNonAttributed())  
      ATTRIBUTED.disabled = true;  
}  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [Concepts](../windows/attributed-programming-concepts.md)   
 [CanAddClass](../ide/canaddclass.md)