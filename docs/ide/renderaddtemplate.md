---
title: "RenderAddTemplate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RenderAddTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RenderAddTemplate 메서드"
ms.assetid: 84c898d6-8676-4ae1-9245-c023e1c9ab92
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# RenderAddTemplate
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 파일을 렌더링합니다. 템플릿 파일을 프로젝트에 추가할 수도 있습니다.  
  
## 구문  
  
```  
  
      function RenderAddTemplate(   
   strTemplateFile,   
   strProjectFile,   
   ProjToAddTo,   
   bOpen    
);  
```  
  
#### 매개 변수  
 *strTemplateFile*  
 TEMPLATES\_PATH와는 달리 경로를 제외한 템플릿 파일 이름입니다.  
  
 *strProjectFile*  
 만든 새 파일 이름입니다.  PROJECT\_PATH와는 달리 이 문자열에는 경로가 포함될 수 있습니다.  
  
 *ProjToAddTo*  
 프로젝트 개체입니다.  만든 파일을 프로젝트에 추가해야 하는 경우에는 프로젝트 이름을 지정합니다. 파일을 프로젝트에 추가하지 않으려면 프로젝트 이름을 지정하지 않거나 **false**를 전달합니다.  
  
 *bOpen*  
 **true**이면 파일을 프로젝트에 추가한 후 기본 편집기에 파일을 엽니다.  
  
## 설명  
 템플릿 파일을 렌더링하거나 프로젝트에 추가하려면 이 함수를 호출합니다.  
  
## 예제  
  
```  
// Declare the project path and the template path.  
var strProjectPath = wizard.FindSymbol("PROJECT_PATH");  
var strTemplatePath = wizard.FindSymbol("TEMPLATES_PATH");  
// Declare the template header and implementation files.  
var strTemplateHeader = wizard.FindSymbol("TEMPLATE_HEADER");  
var strTemplateImpl = wizard.FindSymbol("TEMPLATE_IMPL");  
// Render the template strTemplateHeader and open it in the editor.  
RenderAddTemplate(strTemplateHeader, strHeaderFile, selProj, true);   
// Render the template strTemplateImpl, but do not open it   
// in the editor.  
RenderAddTemplate(strTemplateImpl, strImplFile, selProj, false);  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)