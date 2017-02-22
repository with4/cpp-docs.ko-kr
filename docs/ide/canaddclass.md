---
title: "CanAddClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanAddClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddClass 메서드"
ms.assetid: 76739742-1e34-470c-910d-8784f0adfbf0
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanAddClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자가 실행하려고 하는 코드 마법사와 프로젝트가 호환되는지 검사하기 위해 마법사에서 호출합니다.  
  
## 구문  
  
```  
  
      function CanAddClass(   
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
 클래스를 추가할 수 있으면 **True**이고 그렇지 않으면 **False**입니다.  
  
## 설명  
 이 마법사는 PREPROCESS\_FUNCTION 매개 변수가 [.vsz 파일\(프로젝트 컨트롤\)](../ide/dot-vsz-file-project-control.md)에 있으면 이 함수를 호출합니다.  
  
 또한 [Visual C\+\+ Code Model](http://msdn.microsoft.com/ko-kr/dd6452c2-1054-44a1-b0eb-639a94a1216b) 개체를 사용할 수 있는지 확인합니다.  코드 모델을 사용할 수 없으면 이 함수는 오류를 보고하고 **false**를 반환합니다.  
  
## 예제  
  
```  
// Determine if a class can be added to the project  
if (CanAddClass(selProj, selObj))  
{  
   return true;  
}  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ 마법사에서 사용하는 JScript 함수](../ide/jscript-functions-for-cpp-wizards.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [CanAddMFCClass](../ide/canaddmfcclass.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../ide/ismfcproject.md)