---
title: "GetProjectFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetProjectFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProjectFile 메서드"
ms.assetid: e5fdc468-755a-4b4e-81bd-e63881531bed
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# GetProjectFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 형식을 갖는 파일의 이름을 반환합니다.  
  
## 구문  
  
```  
  
      function GetProjectFile(   
   oProj,   
   strType,   
   bFullPath,   
   bMFC    
);  
```  
  
#### 매개 변수  
 oProj  
 선택한 프로젝트입니다.  
  
 `strType`  
 STDAFX, RC, IDL, CPP, H, ODL 또는 DEF와 같은 검색할 파일 형식입니다.  
  
 *bFullPath*  
 전체 경로 이름을 반환할지를 나타내는 플래그입니다.  
  
 *bMFC*  
 프로젝트가 MFC 기반 프로젝트인지를 나타냅니다.  `strType`가 .cpp 또는 .h이면 프로젝트는 MFC 기반 프로젝트로 취급됩니다.  그렇지 않은 경우 해당 프로젝트는 ATL 기반 프로젝트로 취급됩니다.  
  
## 반환 값  
 지정한 프로젝트에서 해당 형식을 갖는 파일의 이름입니다.  
  
## 설명  
 지정한 프로젝트에서 지정한 형식을 갖는 파일 이름을 구하려면 이 함수를 호출합니다.  
  
## 예제  
  
```  
// The selected MFC project's CPP file is retrieved and   
// assigned to strFileName.  
var strFileName = GetProjectFile(selProj, "CPP", false, true);  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [GetProjectPath](../ide/getprojectpath.md)   
 [GetUniqueFileName](../ide/getuniquefilename.md)