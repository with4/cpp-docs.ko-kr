---
title: "AddATLSupportToProject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddATLSupportToProject 메서드"
ms.assetid: 26708f22-1e9b-4432-83b2-ed94c765b753
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# AddATLSupportToProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL 지원을 MFC 프로젝트에 추가합니다.  
  
## 구문  
  
```  
  
      function AddATLSupportToProject(   
   oProj   
);  
```  
  
#### 매개 변수  
 `oProj`  
 선택한 프로젝트입니다.  
  
## 반환 값  
 ATL 지원이 MFC 프로젝트에 추가되었으면 **true**입니다.  
  
## 설명  
 마법사를 사용하여 만든 MFC 프로젝트에 ATL 지원을 추가하려면 이 함수를 사용합니다.  
  
 마법사에서 MFC 프로젝트에 ATL 지원을 추가할 것인지를 묻는 확인 메시지를 표시합니다.  사용자가 확인하면 마법사에서 기존 지원을 검사한 다음 필요한 모든 GUID, 템플릿, 헤더 및 추가 기능을 추가하므로 마법사를 사용하여 만든 MFC 프로젝트에서 ATL이 지원됩니다.  
  
## 예제  
  
```  
var oCM = selProj.CodeModel;  
var L_TRANSACTION_Text = "Add ATL Support To Project";  
oCM.StartTransaction(L_TRANSACTION_Text);  
var bRet = AddATLSupportToProject(selProj);  
if (bRet)  
   oCM.CommitTransaction();  
else  
   oCM.AbortTransaction();  
return bRet;  
```  
  
## 참고 항목  
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../ide/ismfcproject.md)   
 [ATL 소개](../atl/introduction-to-atl.md)