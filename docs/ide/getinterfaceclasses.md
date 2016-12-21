---
title: "GetInterfaceClasses | Microsoft Docs"
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
  - "GetInterfaceClasses"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInterfaceClasses 메서드"
ms.assetid: 712c112f-b4ff-43c4-ad49-c4f4c13c48bd
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetInterfaceClasses
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터페이스와 연관된 `VCCodeClass` 개체를 반환합니다.  
  
## 구문  
  
```  
  
      function GetInterfaceClasses(   
   strInterface,   
   oProject,   
   aryClasses    
);  
```  
  
#### 매개 변수  
 *strInterface*  
 클래스 개체가 포함된 인터페이스의 이름입니다.  
  
 *oProject*  
 선택한 프로젝트입니다.  
  
 *aryClasses*  
 \[out\] 인터페이스에 있는 클래스 개체의 배열입니다.  
  
## 반환 값  
 인터페이스와 연관된 <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeClass> 개체입니다.  
  
## 설명  
 인터페이스와 연관된 클래스를 검색하려면 이 함수를 호출합니다.  
  
## 예제  
  
```  
var aryClasses = new Array();  
GetInterfaceClasses(oInterface.Name, selProj, aryClasses);  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [GetInterfaceType](../ide/getinterfacetype.md)