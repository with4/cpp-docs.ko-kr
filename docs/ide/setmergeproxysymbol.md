---
title: "SetMergeProxySymbol | Microsoft Docs"
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
  - "SetMergeProxySymbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetMergeProxySymbol 메서드"
ms.assetid: d6a9db59-2d5b-4431-98bc-785675e0eafe
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SetMergeProxySymbol
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 함수는 필요한 경우 \_MERGE\_PROXYSTUB 기호를 추가하기 위해 마법사에서 호출합니다.  
  
## 구문  
  
```  
  
      function SetMergeProxySymbol(   
   oProj    
);  
```  
  
#### 매개 변수  
 `oProj`  
 선택한 프로젝트 개체입니다.  
  
## 설명  
 이 함수는 필요한 경우 \_MERGE\_PROXYSTUB 기호를 추가하기 위해 마법사에서 호출합니다.  
  
## 예제  
  
```  
SetMergeProxySymbol (selproj);  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)