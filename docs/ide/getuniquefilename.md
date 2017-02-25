---
title: "GetUniqueFileName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetUniqueFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetUniqueFilename 메서드"
ms.assetid: f9760e1a-82d0-4d8b-b00a-6f4c36f6b2c6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# GetUniqueFileName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

고유한 파일 이름을 반환합니다.  
  
## 구문  
  
```  
  
      function GetUniqueFileName(   
   strDirectory,   
   strFileName    
);  
```  
  
#### 매개 변수  
 *strDirectory*  
 파일 이름을 찾을 디렉터리입니다.  
  
 `strFileName`  
 검사할 파일 이름입니다.  
  
## 반환 값  
 파일 이름이 고유할 경우 `strFileName`에 지정한 파일 이름을 반환합니다. 그렇지 않으면 이 함수는 `strFileName`에 1에서 9999999까지의 번호를 추가하여 고유하게 만든 파일 이름을 반환합니다.  `strFileName`을 지정하지 않으면 이 함수는 [GetTempName 메서드](jsmthGetTempName)를 사용하여 고유한 파일 이름을 반환합니다.  
  
## 설명  
 고유한 파일 이름을 반환합니다.  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [GetProjectFile](../ide/getprojectfile.md)