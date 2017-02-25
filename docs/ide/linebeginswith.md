---
title: "LineBeginsWith | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LineBeginsWith"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LineBeginsWith 메서드"
ms.assetid: cbdd08ad-7309-4504-9f23-1c22bb3e4bd0
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# LineBeginsWith
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

특정 줄이 지정한 문자열로 시작하는지 확인하기 위해 [InsertIntoFunction](../ide/insertintofunction.md)에서 호출됩니다.  
  
## 구문  
  
```  
  
      function LineBeginsWith(   
   strBody,   
   strSearchString,   
   nStartPos    
);  
```  
  
#### 매개 변수  
 *strBody*  
 함수의 본문입니다.  
  
 `strSearchString`  
 찾을 문자열입니다.  
  
 *nStartPos*  
 검색을 시작할 위치입니다.  
  
## 반환 값  
 문자열을 찾으면 **true**이고 그렇지 않으면 **false**입니다.  
  
## 설명  
 지정한 줄이 지정한 문자열로 시작되는지 확인하기 위해 `InsertIntoFunction`에서 호출되는 함수입니다.  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [OffsetToLineNumber](../ide/offsettolinenumber.md)