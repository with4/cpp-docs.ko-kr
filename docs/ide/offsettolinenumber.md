---
title: "OffsetToLineNumber | Microsoft Docs"
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
  - "OffsetToLineNumber"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OffsetToLineNumber 함수"
ms.assetid: ac7e3c22-6b3b-432c-85cc-b50bbef9ce8c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OffsetToLineNumber
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

함수 본문에 있는 인덱스를 줄 번호로 변환하기 위해 [InsertIntoFunction](../ide/insertintofunction.md)에서 호출됩니다.  
  
## 구문  
  
```  
  
      function OffsetToLineNumber(   
   strString,   
   nPos    
);  
```  
  
#### 매개 변수  
 `strString`  
 함수 본문이 포함된 문자열입니다.  함수 본문은 각 줄이 CR\-LF 문자 쌍으로 구분되어 있는 여러 줄로 구성된 문자열입니다.  
  
 `nPos`  
 문자열 내의 위치입니다.  
  
## 반환 값  
 `nPos`이 있는 함수 본문 내의 줄입니다.  함수의 첫 번째 줄은 0이 아닌 1로 취급됩니다.  
  
## 설명  
 함수 본문에서 지정한 위치의 줄 번호를 찾습니다.  
  
 함수 본문에서 `nPos`에 있는 인덱스를 줄 번호로 변경하기 위해 `InsertIntoFunction`에서 호출되는 함수입니다.  
  
## 예제  
  
```  
strString = "function DelFile(fso,  
 strWizTempFile)\r\n{\r\n\ttry\r\n\t{\r\nif   
(fso.FileExists(strWizTempFile))\r\nreturn true;\r\n";  
  
nLine =  OffsetToLineNumber(strString, 60);  
  
// The return value for the above is 5, because character 60 in the string   
// occurs in the 5th line within the string.  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [LineBeginsWith](../ide/linebeginswith.md)