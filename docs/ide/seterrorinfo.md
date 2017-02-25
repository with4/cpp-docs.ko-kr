---
title: "SetErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetErrorInfo 메서드"
ms.assetid: 78bca763-3f90-4e04-b566-b4b7fe2431b1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# SetErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 오류 정보를 제공하기 위해 [OnWizFinish](../ide/onwizfinish.md) 및 [CanUseFileName](../ide/canusefilename.md)에서 호출됩니다.  
  
## 구문  
  
```  
  
      function SetErrorInfo(   
   oErrorObj   
);  
```  
  
#### 매개 변수  
 *oErrorObj*  
 오류 개체입니다.  
  
## 설명  
 현재 오류 정보를 제공하기 위해 [OnWizFinish](../ide/onwizfinish.md) 및 [CanUseFileName](../ide/canusefilename.md)에서 호출됩니다.  자세한 내용은 Visual C\+\+ 마법사 모델 설명서의 <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.SetErrorInfo%2A>를 참조하십시오.  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)