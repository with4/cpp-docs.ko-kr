---
title: "Dialog Editor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.dialog.dialog"
  - "vc.editors.dialog.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource editors, Dialog editor"
  - "editors, dialog boxes"
  - "Dialog editor"
  - "dialog boxes, editing"
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Dialog Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대화 상자 편집기에서는 대화 상자 리소스를 만들거나 편집할 수 있습니다. 리소스 뷰\(**보기 &#124; 리소스 뷰**\) 창에서 대화 상자의 .rc 파일을 두 번 클릭하여 대화 상자 편집기를 엽니다. Express 버전에서는 리소스 뷰를 사용할 수 없습니다.  
  
 새 대화 상자\(또는 대화 상자 템플릿\)를 만드는 첫 번째 단계 중 하나는 대화 상자에 컨트롤을 추가하는 것입니다. 대화 상자 편집기에서 특정 크기, 모양 또는 맞춤에 맞게 컨트롤을 정렬하거나 대화 상자 내에서 작동하도록 이동할 수 있습니다. 또한 컨트롤을 쉽게 삭제할 수 있습니다.  
  
 대화 상자를 템플릿으로 저장하여 다시 사용할 수 있습니다. 대화 상자 디자인과 이를 구현하는 코드 편집 간을 쉽게 전환할 수도 있습니다.  
  
 대화 상자 편집기에서 단일 또는 여러 컨트롤의 속성을 편집할 수도 있습니다. 탭 순서 즉, Tab 키를 누를 때 컨트롤이 포커스를 받는 순서를 변경하거나, 사용자가 키보드를 사용하여 컨트롤을 선택할 수 있도록 하는 액세스 키\(키 조합\)를 정의할 수 있습니다. 미리 설정된 액세스 키 목록은 [대화 상자 편집기의 액셀러레이터 키](../mfc/accelerator-keys-for-the-dialog-editor.md)를 참조하세요.  
  
 대화 상자 편집기에서는 ActiveX 컨트롤을 포함하여 사용자 지정 컨트롤을 사용할 수도 있습니다. 또한 [폼 보기](../mfc/reference/cformview-class.md), [레코드 뷰](../data/record-views-mfc-data-access.md) 또는 [대화 상자 모음](../mfc/dialog-bars.md)을 편집할 수 있습니다.  
  
 [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)]부터는 대화 상자 편집기를 통해 동적 레이아웃을 정의하여 사용자가 대화 상자의 크기를 조정할 때 컨트롤이 이동하고 크기 조정되는 방식을 지정할 수 있습니다. 자세한 내용은 [동적 레이아웃](../mfc/dynamic-layout.md)을 참조하세요.  
  
-   [새 대화 상자 만들기](../mfc/creating-a-new-dialog-box.md)  
  
-   [런타임에 사용자가 종료할 수 없는 대화 상자 만들기](../mfc/creating-a-dialog-box-that-users-cannot-exit.md)  
  
-   [대화 상자 편집기 도구 모음 표시 또는 숨기기](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md)  
  
-   [대화 상자 편집기와 코드 간 전환](../mfc/switching-between-dialog-box-controls-and-code.md)  
  
-   [대화 상자의 컨트롤](../mfc/controls-in-dialog-boxes.md)  
  
-   [대화 상자 컨트롤에 사용할 이벤트 처리기 추가](../mfc/adding-event-handlers-for-dialog-box-controls.md)  
  
-   [대화 상자 테스트](../mfc/testing-a-dialog-box.md)  
  
-   [대화 상자 편집기의 액셀러레이터 키](../mfc/accelerator-keys-for-the-dialog-editor.md)  
  
-   [대화 상자 편집기 문제 해결](../mfc/troubleshooting-the-dialog-editor.md)  
  
    > [!TIP]
    >  대부분 대화 상자 편집기를 사용할 때 마우스 오른쪽 단추를 클릭하여 자주 사용하는 명령의 바로 가기 메뉴를 표시할 수 있습니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Resource Editors](../mfc/resource-editors.md)   
 [컨트롤](../mfc/controls-mfc.md)   
 [컨트롤 클래스](../mfc/control-classes.md)   
 [대화 상자 클래스](../mfc/dialog-box-classes.md)   
 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)