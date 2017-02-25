---
title: "SetNoPchSettings | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetNoPchSettings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetNoPchSettings 메서드"
ms.assetid: 52373c98-ad5e-4e9b-9e0f-9f58ddb2a636
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# SetNoPchSettings
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

미리 컴파일된 헤더를 사용하지 않는 경우 프로젝트 구성 속성을 설정합니다.  
  
## 구문  
  
```  
  
      function SetNoPchSettings(   
   oProj    
);  
```  
  
#### 매개 변수  
 `oProj`  
 선택한 프로젝트입니다.  
  
## 설명  
 프로젝트에서 미리 컴파일된 헤더 설정을 사용하지 않는 경우 프로젝트를 구성하려면 이 함수를 호출합니다.  
  
## 예제  
 [SetCommonPchSettings](../ide/setcommonpchsettings.md)를 참조하십시오.  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [SetCommonPchSettings](../ide/setcommonpchsettings.md)   
 [AddCommonConfig](../ide/addcommonconfig.md)