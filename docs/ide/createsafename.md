---
title: "CreateSafeName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CreateSafeName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateSafeName 메서드"
ms.assetid: 3a0dd4af-776d-4c25-aff9-4c539f173cb8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CreateSafeName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 이름을 생성합니다.  
  
## 구문  
  
```  
  
      function CreateSafeName(   
   strName    
);  
```  
  
#### 매개 변수  
 `strName`  
 이전 이름입니다.  
  
## 반환 값  
 안전한 새 이름입니다.  
  
## 설명  
 C\+\+에서 사용할 수 없는 문자가 포함된 이름을 C\+\+ 이름으로 만들려면 이 함수를 호출합니다.  C\+\+ 이름에는 대\/소문자, 숫자, 밑줄\("\_"\)을 사용할 수 있습니다.  
  
 이 함수를 사용하면 사용할 수 없는 모든 문자는 제외하고 문자 단위로 이전 이름을 검사할 수 있습니다.  이전 이름에 사용할 수 있는 문자가 없으면 이 함수는 새 이름으로 "My"를 반환합니다.  새 이름이 숫자로 시작되면 이 함수는 새 이름 앞에 "My"를 추가합니다.  
  
## 예제  
  
```  
// Get the project name  
var strProjectName = wizard.FindSymbol("PROJECT_NAME");  
  
// Set the project name to the safe project name.   
var strSafeProjectName = CreateSafeName(strProjectName);  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)