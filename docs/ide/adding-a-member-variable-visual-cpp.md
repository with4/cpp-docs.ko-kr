---
title: "멤버 변수 추가(Visual C++) | Microsoft Docs"
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
  - "vc.codewiz.classes.member.variable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "멤버 변수"
  - "멤버 변수, 추가"
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 멤버 변수 추가(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스 뷰를 사용하여 클래스에 멤버 변수를 추가할 수 있습니다.  멤버 변수는 [데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)를 위한 것이나 일반적인 것일 수 있습니다.  데이터 멤버 변수 마법사는 관련 정보를 가져와서 해당하는 위치의 소스 파일에 요소를 삽입하는 데 사용하기 위해 특수하게 디자인되었습니다.  [리소스 뷰](../windows/resource-view-window.md)의 [대화 상자 편집기](../mfc/dialog-editor.md) 또는 [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 멤버 변수를 추가할 수 있습니다.  
  
> [!NOTE]
>  대화 상자를 디자인하고 구현할 경우 대화 상자 편집기를 사용하여 대화 상자 컨트롤을 추가한 다음 컨트롤의 멤버 변수를 구현하는 것이 더 효율적입니다.  
  
### 멤버 변수 추가 마법사를 사용하여 리소스 뷰에서 대화 상자 컨트롤의 멤버 변수를 추가하려면  
  
1.  리소스 뷰에서 프로젝트 노드와 Dialog 노드를 확장하여 프로젝트의 대화 상자 목록을 표시합니다.  
  
2.  멤버 변수를 추가할 대화 상자를 두 번 클릭하여 대화 상자 편집기에서 엽니다.  
  
3.  대화 상자 편집기에 표시된 대화 상자에서 멤버 변수를 추가할 컨트롤을 마우스 오른쪽 단추로 클릭합니다.  
  
4.  바로 가기 메뉴에서 **변수 추가**를 클릭하여 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md)를 표시합니다.  
  
    > [!NOTE]
    >  **컨트롤 ID**에는 이미 기본값이 입력되어 있습니다.  
  
5.  해당 마법사 상자에 정보를 입력합니다.  자세한 내용은 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)을 참조하십시오.  
  
6.  **마침**을 클릭하여 정의 및 구현 코드를 프로젝트에 추가하고 마법사를 닫습니다.  
  
### 멤버 변수 추가 마법사를 사용하여 클래스 뷰에서 멤버 변수를 추가하려면  
  
1.  [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 프로젝트 노드를 확장하여 프로젝트의 클래스를 표시합니다.  
  
2.  변수를 추가할 클래스를 마우스 오른쪽 단추로 클릭합니다.  
  
3.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **변수 추가**를 클릭하여 멤버 변수 추가 마법사를 표시합니다.  
  
4.  해당 마법사 상자에 정보를 입력합니다.  자세한 내용은 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md)를 참조하십시오.  
  
5.  **마침**을 클릭하여 정의 및 구현 코드를 프로젝트에 추가하고 마법사를 닫습니다.  
  
## 참고 항목  
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../ide/navigating-the-class-structure-visual-cpp.md)