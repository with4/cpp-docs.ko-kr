---
title: "GetInterfaceType | Microsoft Docs"
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
  - "GetInterfaceType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInterfaceType 메서드"
ms.assetid: cc6403a8-0c2b-47f7-a8f7-9db95df87d5a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetInterfaceType
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터페이스의 형식입니다.  
  
## 구문  
  
```  
  
      function GetInterfaceType(   
   oInterface    
);  
```  
  
#### 매개 변수  
 *oInterface*  
 <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeInterface> 개체  
  
## 반환 값  
 custom, dual, dispinterfaces 및 oleautomation과 같은 인터페이스 형식을 나타내는 문자열입니다.  
  
## 설명  
 인터페이스 형식을 가져오려면 이 함수를 호출합니다.  
  
## 예제  
 [GetMaxID](../ide/getmaxid.md)를 참조하십시오.  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [GetInterfaceClasses](../ide/getinterfaceclasses.md)