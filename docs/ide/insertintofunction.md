---
title: "InsertIntoFunction | Microsoft Docs"
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
  - "InsertIntoFunction"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InsertIntoFunction 메서드"
ms.assetid: 50500c3c-bee3-4a9c-a403-7dcd752de23c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InsertIntoFunction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[InitInstance](../Topic/CWinApp::InitInstance.md)에 코드를 삽입하기 위해 [AddATLSupportToProject](../ide/addatlsupporttoproject.md)에서 사용합니다.  
  
## 구문  
  
```  
  
      function InsertIntoFunction(   
   oFunction,   
   strSearchString,   
   nStartLine,   
   nEndLine,   
   bInsideIfBlock    
);  
```  
  
#### 매개 변수  
 *oFunction*  
 코드를 삽입할 함수 개체입니다.  
  
 `strSearchString`  
 삽입 포인트를 결정하기 위해 찾을 문자열입니다.  
  
 *nStartLine*  
 [GetCodeForInitInstance](../ide/getcodeforinitinstance.md)에 전달할 시작 줄입니다.  
  
 *nEndLine*  
 [GetCodeForInitInstance](../ide/getcodeforinitinstance.md)에 전달할 마지막 줄입니다.  
  
 *bInsideIfBlock*  
 함수 블록에 삽입할 것인지를 나타냅니다.  
  
## 반환 값  
 삽입할 수 있으면 **true**이고 그렇지 않으면 **false**입니다.  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [GetMemberfunction](../ide/getmemberfunction.md)