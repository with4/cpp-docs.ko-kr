---
title: "대화 상자에서 공용 컨트롤 사용 | Microsoft Docs"
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
  - "공용 컨트롤[C++], 대화 상자"
  - "대화 상자 컨트롤[C++], 공용 컨트롤"
  - "Windows 공용 컨트롤[C++], 대화 상자"
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 대화 상자에서 공용 컨트롤 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows 공용 컨트롤들은 [대화 상자](../mfc/dialog-boxes.md), 보기, 기록 보기 및 대화상자 템플릿에 기반한 다른 창에서 사용됩니다.  작은 변화와 다음과 같은 프로스저는 폼에도 잘 작동될 것입니다.  
  
## 절차  
  
#### 대화상자에서 공용 컨트롤을 사용하기 위해  
  
1.  [대화상자 편집기를 사용하여](../mfc/using-the-dialog-editor-to-add-controls.md) 대화 상자 템플릿에 컨트롤을 추가합니다.  
  
2.  컨트롤을 나타내는 멤버 변수를 대화 상자 클래스에 추가 합니다.  **멤버 변수 추가** 대화 상자에서 **제어 변수**를 체크하고 **컨트롤**이 **범주**에 대해 선택되었는지 확인합니다.  
  
3.  이 공용 컨트롤이 프로그램에 입력을 제공 하는 경우 추가 멤버 선언 들을 처리 하는 대화 상자 클래스에 변수 값을 입력 합니다.  
  
    > [!NOTE]
    >  클래스 뷰에서 컨텍스트 메뉴를 사용하여 이러한 멤버 변수를 추가할 수 있습니다 \([멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)참조\).  
  
4.  사용자의 대화상자 클래스에 대한 [OnInitDialog](../Topic/CDialog::OnInitDialog.md)에서 공용 컨트롤에 대 한 초기 조건을 설정 합니다.  이전 단계에서 만든 멤버 변수를 사용하여 멤버 함수를 초기 값 및 기타 설정을 설정하기위해 사용합니다.  설정에 대 한 자세한 내용은 해당 컨트롤의 다음 설명을 참조하세요.  
  
     사용자는 또한 [대화 상자 데이터 교환](../mfc/dialog-data-exchange-and-validation.md) \(DDX\)를 대화 상자에서 컨트롤을 초기화하기위해 사용할 수 있습니다.  
  
5.  대화 상자의 컨트롤에 대 한 처리기에서 컨트롤을 조작하기 위해 멤버변수를 사용합니다.  설정에 대 한 자세한 내용은 해당 컨트롤의 다음 설명을 참조하세요.  
  
    > [!NOTE]
    >  대화상자가 자체로 존재하는 동안에만 멤버변수는 존재합니다.  대화 상자를 닫으면 입력된 값에 대해 컨트롤을 쿼리할 수 없습니다.  공용 컨트롤에서 입력된 값을 사용 하려면 대화 상자 클래스에서 `OnOK` 을 재정의 하세요.  재정의에서 입력된 값에 대한 컨트롤을 쿼리하고 대화 상자 클래스의 멤버 변수에 값을 저장 합니다.  
  
    > [!NOTE]
    >  대화 상자의 컨트롤로부터 값을 회수하거나 설정하기 위해 데이터 교환 대화상자를 사용할 수 있습니다.  
  
## 설명  
 대화상자에 일부 일반 컨트롤의 추가는 더 이상 함수가 작동 하지 않는 경우에 대화상자에 발생 합니다.  이 상황을 처리하는 것에 대한 더 자세한 내용은 [Adding Controls to a Dialog Causes the Dialog to No Longer Function](../mfc/adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function.md)을 참조하세요.  
  
## 수행할 작업  
  
-   [대화상자 에디터 대신에 직접 대화상자에 컨트롤을 추가하세요.](../mfc/adding-controls-by-hand.md)  
  
-   [표준 Windows 공용 컨트롤 중 하나에서 컨트롤을 파생하세요.](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [공용 컨트롤을 자식 창으로 사용하세요.](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [컨트롤에서 알림 메시지 받기](../mfc/receiving-notification-from-common-controls.md)  
  
-   [데이터 교환 대화상자를 사용하세요\(DDX\)](../mfc/dialog-data-exchange-and-validation.md)  
  
## 참고 항목  
 [컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)   
 [컨트롤](../mfc/controls-mfc.md)