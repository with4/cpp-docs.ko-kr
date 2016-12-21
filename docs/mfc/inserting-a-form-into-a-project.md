---
title: "프로젝트에 폼 삽입 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "폼, 프로젝트에 추가"
  - "새로 삽입 대화 상자"
  - "폼 삽입"
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 프로젝트에 폼 삽입
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Forms provide a convenient container for controls.  You can easily insert an MFC\-based form into your application as long as the application supports the MFC libraries.  
  
### To insert a form into your project  
  
1.  From Class View, select the project to which you want to add the form, and click the right mouse button.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.  
  
     If the **New Form** command is not available, your project may be based on the Active Template Library \(ATL\).  To add a form to an ATL project, you must [specify certain settings](../atl/reference/application-settings-atl-project-wizard.md) when first creating the project.  
  
3.  From the **MFC** folder, click **MFC Class**.  
  
4.  Using the MFC Class Wizard, make the new class derive from [CFormView](../mfc/reference/cformview-class.md).  
  
 Visual C\+\+ adds the form to your application, opening it inside the Dialog editor so that you can begin adding controls and working on its overall design.  
  
 You may want to perform the following additional steps \(not applicable for dialog\-based applications\):  
  
1.  Override the `OnUpdate` member function.  
  
2.  Implement a member function to move data from your view to your document.  
  
3.  Create an `OnPrint` member function.  
  
## 참고 항목  
 [폼 뷰](../mfc/form-views-mfc.md)