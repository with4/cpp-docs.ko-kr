---
title: "OnWizFinish | Microsoft Docs"
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
  - "OnWizFinish"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnWizFinish 메서드"
ms.assetid: 5e0790c3-c5b4-43de-b9db-b18d07c19f41
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OnWizFinish
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자가 **마침**을 클릭할 때 마법사 HTML 스크립트에서 호출됩니다.  이 함수는 호출된 후 마법사 컨트롤의 **Finish** 함수를 호출합니다.  
  
## 구문  
  
```  
  
      function OnWizFinish(   
   document    
);  
```  
  
#### 매개 변수  
 `document`  
 HTML 문서 개체입니다.  
  
## 설명  
 사용자가 **마침**을 클릭할 때 마법사 HTML 스크립트에서 호출되는 함수입니다.  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)