---
title: "새 컨트롤 클래스 기반의 변수 선언 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.classes.control.variable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클래스[C++], 클래스 기반의 변수 선언"
  - "컨트롤 클래스, 변수"
  - "변수, 컨트롤 클래스"
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 새 컨트롤 클래스 기반의 변수 선언
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC 컨트롤 클래스를 만들었으면 해당 클래스에 따라 변수를 선언할 수 있습니다.  새 변수에 대한 컨텍스트를 제공하려면 대화 상자 편집기를 연 다음 다시 사용할 수 있는 컨트롤을 사용할 대화 상자를 편집합니다.  또한 관련된 클래스가 대화 상자에 이미 있어야 합니다.  대화 상자 편집기를 사용하는 방법에 대한 자세한 내용은 [대화 상자 편집기](../../mfc/dialog-editor.md)를 참조하십시오.  
  
### 다시 사용할 수 있는 클래스에 따라 변수를 선언하려면  
  
1.  대화 상자를 편집하면서 새 컨트롤의 기본 클래스와 같은 형식을 가진 컨트롤을 컨트롤 도구 모음에서 대화 상자로 끌어 놓습니다.  
  
2.  끌어 놓은 컨트롤 위에 마우스 포인터를 놓습니다.  
  
3.  Ctrl 키를 누른 채 해당 컨트롤을 두 번 클릭합니다.  
  
     [멤버 변수 추가](../../ide/add-member-variable-wizard.md) 대화 상자가 나타납니다.  
  
4.  **액세스** 상자에서 컨트롤에 해당하는 액세스 권한을 선택합니다.  
  
5.  **컨트롤 변수** 확인란을 클릭합니다.  
  
6.  **변수 이름** 상자에 이름을 입력합니다.  
  
7.  **범주**에서 **컨트롤**을 클릭합니다.  
  
8.  **컨트롤 ID** 목록에서, 추가한 컨트롤을 선택합니다.  **변수 형식** 목록에는 해당 변수 형식이 표시되고 **컨트롤 형식** 상자에는 해당 컨트롤 형식이 표시되어야 합니다.  
  
9. **주석** 상자에서 코드에 표시할 주석을 추가합니다.  
  
10. **확인**을 클릭합니다.  
  
## 참고 항목  
 [함수에 메시지 매핑](../../mfc/reference/mapping-messages-to-functions.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../../ide/navigating-the-class-structure-visual-cpp.md)