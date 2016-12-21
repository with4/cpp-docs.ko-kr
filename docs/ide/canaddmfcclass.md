---
title: "CanAddMFCClass | Microsoft Docs"
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
  - "CanAddMFCClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddMFCClass 메서드"
ms.assetid: 6a97a410-b028-4aad-9b06-04c12cf481eb
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CanAddMFCClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자가 MFC 클래스를 프로젝트에 추가할 수 있는지 검사하기 위해 마법사가 호출합니다.  
  
## 구문  
  
```  
  
      function CanAddMFCClass(   
   oProj,   
   oObject    
);  
```  
  
#### 매개 변수  
 `oProj`  
 선택한 프로젝트입니다.  
  
 `oObject`  
 선택한 개체입니다.  이 경우에는 현재 프로젝트입니다.  
  
## 반환 값  
 클래스를 추가할 수 있으면 **true**이고 사용자가 MFC 프로젝트가 아니며 MFC 지원이 없는 프로젝트에 대해 함수를 호출하면 **false**입니다.  
  
## 설명  
 프로젝트가 실행될 코드 마법사와 호환되는지 확인하기 위해 마법사에서 호출됩니다. MFC 클래스를 사용할 수 있습니다.  
  
 마법사는 PREPROCESS\_FUNCTION 매개 변수가 [.vsz 파일\(프로젝트 컨트롤\)](../ide/dot-vsz-file-project-control.md)에 있으면 이 함수를 호출한 다음 [Visual C\+\+ Code Model](http://msdn.microsoft.com/ko-kr/dd6452c2-1054-44a1-b0eb-639a94a1216b) 개체를 사용할 수 있는지 확인합니다.  코드 모델을 사용할 수 없으면 이 함수는 오류를 보고하고 **false**를 반환합니다.  
  
## 예제  
  
```  
// Determine if an MFC class can be added to the project  
if (CanAddMFCClass(selProj, selObj))  
{  
   return true;  
}  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [CanAddClass](../ide/canaddclass.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../ide/ismfcproject.md)