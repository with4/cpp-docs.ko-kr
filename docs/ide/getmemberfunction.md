---
title: "GetMemberfunction | Microsoft Docs"
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
  - "GetMemberFunction"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMemberfunction 메서드"
ms.assetid: 1e610977-9bc7-4ff2-a79f-132c8e913b4d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetMemberfunction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정한 이름에 따라 함수 개체를 가져오려면 이 함수를 호출합니다.  
  
## 구문  
  
```  
  
      function GetMemberfunction(   
   oClass,   
   strFuncName,   
   oProj    
);  
```  
  
#### 매개 변수  
 *oClass*  
 선택한 클래스 개체입니다.  
  
 `strFuncName`  
 함수 이름  
  
 `oProj`  
 선택한 프로젝트입니다.  
  
## 반환 값  
 `strFuncName`으로 지정된 함수입니다.  
  
## 설명  
 지정한 이름에 따라 함수 개체를 가져오려면 이 함수를 호출합니다.  자세한 내용은 Visual C\+\+ 코드 모델의 <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeModel.Functions%2A>를 참조하십시오.  
  
## 예제  
  
```  
// Gets the function ExitInstance from the class CWinApp in the   
// current project.  
var oExitInstance = GetMemberFunction(oCWinApp, "ExitInstance", oProj);  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)