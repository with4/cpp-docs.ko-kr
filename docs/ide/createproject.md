---
title: "CreateProject | Microsoft Docs"
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
  - "CreateProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateProject 메서드"
ms.assetid: b5598b46-fe29-4ad0-8bfe-a4dc789aeebd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CreateProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 프로젝트를 만듭니다.  
  
## 구문  
  
```  
  
      function CreateProject(   
   strProjectName,   
   strProjectPath    
);  
```  
  
#### 매개 변수  
 `strProjectName`  
 프로젝트 이름이 들어 있는 문자열입니다.  
  
 *strProjectPath*  
 프로젝트 경로가 들어 있는 문자열입니다.  
  
## 반환 값  
 프로젝트 개체입니다.  
  
## 설명  
 Visual Studio에서 열 수 있는 C\+\+ 프로젝트를 만들려면 이 함수를 호출합니다.  마법사의 컨텍스트 매개 변수 **WizardType**이 **vsWizardAddSubProject**로 지정되어 있으면 프로젝트는 기존 프로젝트의 하위 프로젝트로 추가됩니다.  자세한 내용은 [ContextParams 열거형](../Topic/Context%20Parameters%20for%20Launching%20Wizards.md)을 참조하십시오.  
  
## 예제  
 [AddFilesToProject](../ide/addfilestoproject.md)를 참조하십시오.  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)