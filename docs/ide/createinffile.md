---
title: "CreateInfFile | Microsoft Docs"
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
  - "CreateInfFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInfFile 메서드"
ms.assetid: 941ea2ce-db10-428e-b423-8dc2a7e825cf
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CreateInfFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

마법사의 Templates.inf 파일을 만듭니다.  
  
## 구문  
  
```  
  
function CreateInfFile( );  
  
```  
  
## 반환 값  
 마법사 템플릿 파일입니다.  
  
## 설명  
 사용자가 선택한 내용에 따라 마법사에서 일단 임시 디렉터리에 만드는 임시 텍스트 파일인 Templatesinf.txt에서 해당 마법사의 Template.inf 파일을 만들려면 이 함수를 호출합니다.  Templates.inf에는 마법사에서 만드는 파일 이름의 목록이 들어 있습니다.  자세한 내용은 [템플릿 파일](../ide/template-files.md)을 참조하십시오.  
  
 이 함수를 사용해서 임시 디렉터리에 Templatesinf.txt 파일을 만들 수 없으면 오류가 표시됩니다.  
  
## 예제  
 [AddFilesToProject](../ide/addfilestoproject.md)를 참조하십시오.  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [AddFilesToProject](../ide/addfilestoproject.md)   
 [SetFilters](../ide/setfilters.md)   
 [AddFilesToProject](../ide/addfilestoproject.md)