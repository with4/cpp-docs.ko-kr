---
title: "GetMaxID | Microsoft Docs"
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
  - "GetMaxID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMaxID 메서드"
ms.assetid: a155ec2e-6132-4e40-9b85-d710538778a1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetMaxID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 인터페이스의 멤버와 모든 기본 멤버에서 가장 높은 dispid 값을 반환합니다.  
  
## 구문  
  
```  
  
      function GetMaxID(   
   ointerface    
);  
```  
  
#### 매개 변수  
 *ointerface*  
 <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeInterface> 개체  
  
## 반환 값  
 이 *oInterface*의 멤버와 모든 기본 멤버에서 가장 높은 dispid 값입니다.  
  
## 설명  
 이 인터페이스의 멤버와 모든 기본 멤버에서 가장 높은 dispid 값을 가져오려면 이 함수를 호출합니다.  
  
## 예제  
  
```  
if (strInterfaceType == "custom")  
      window.external.AddSymbol("DISPID_DISABLED", true);  
   else  
   {  
      var nDispID = window.external.FindSymbol("DISPID");  
      if (!nDispID.length)  
      {  
         nDispID = GetMaxID(oInterface) + 1;  
         window.external.AddSymbol("DISPID", nDispID);  
      }  
   }  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)