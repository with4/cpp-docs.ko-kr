---
title: "대화 상자 편집기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
dev_langs: C++
helpviewer_keywords:
- resource editors, Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes, editing
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a18ed3aad1d3a9ea697ac815658b5eba8d99bff1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-editor"></a>대화 상자 편집기
대화 상자 편집기에서는 대화 상자 리소스를 만들거나 편집할 수 있습니다. 리소스 뷰 창에서 대화 상자의.rc 파일을 두 번 클릭 하 여 대화 상자 편집기를 엽니다 (**보기 &#124; 리소스 뷰**). Express 버전에서는 리소스 뷰를 사용할 수 없습니다.  
  
 새 대화 상자(또는 대화 상자 템플릿)를 만드는 첫 번째 단계 중 하나는 대화 상자에 컨트롤을 추가하는 것입니다. 대화 상자 편집기에서 특정 크기, 모양 또는 맞춤에 맞게 컨트롤을 정렬하거나 대화 상자 내에서 작동하도록 이동할 수 있습니다. 또한 컨트롤을 쉽게 삭제할 수 있습니다.  
  
 대화 상자를 템플릿으로 저장하여 다시 사용할 수 있습니다. 대화 상자 디자인과 이를 구현하는 코드 편집 간을 쉽게 전환할 수도 있습니다.  
  
 대화 상자 편집기에서 단일 또는 여러 컨트롤의 속성을 편집할 수도 있습니다. 탭 순서 즉, Tab 키를 누를 때 컨트롤이 포커스를 받는 순서를 변경하거나, 사용자가 키보드를 사용하여 컨트롤을 선택할 수 있도록 하는 액세스 키(키 조합)를 정의할 수 있습니다. 미리 설정된 액세스 키 목록은 [대화 상자 편집기의 액셀러레이터 키](../windows/accelerator-keys-for-the-dialog-editor.md)를 참조하세요.  
  
 대화 상자 편집기에서는 ActiveX 컨트롤을 포함하여 사용자 지정 컨트롤을 사용할 수도 있습니다. 또한 [폼 보기](../mfc/reference/cformview-class.md), [레코드 뷰](../data/record-views-mfc-data-access.md)또는 [대화 상자 모음](../mfc/dialog-bars.md)을 편집할 수 있습니다.  
  
 Visual Studio 2015 이상에서는 동적 레이아웃 컨트롤 이동한 사용자는 대화 상자 크기를 조정할 때의 크기를 조정 지정을 정의 하는 대화 상자 편집기를 사용할 수 있습니다. 자세한 내용은 [Dynamic Layout](../mfc/dynamic-layout.md)을 참조하세요.  
  
-   [새 대화 상자 만들기](../windows/creating-a-new-dialog-box.md)  
  
-   [런타임에 사용자가 종료할 수 없는 대화 상자 만들기](../windows/creating-a-dialog-box-that-users-cannot-exit.md)  
  
-   [대화 상자 편집기 도구 모음 표시 또는 숨기기](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)  
  
-   [대화 상자 편집기와 코드 간 전환](../windows/switching-between-dialog-box-controls-and-code.md)  
  
-   [대화 상자의 컨트롤](../windows/controls-in-dialog-boxes.md)  
  
-   [대화 상자 컨트롤에 사용할 이벤트 처리기 추가](../windows/adding-event-handlers-for-dialog-box-controls.md)  
  
-   [대화 상자 테스트](../windows/testing-a-dialog-box.md)  
  
-   [대화 상자 편집기의 액셀러레이터 키](../windows/accelerator-keys-for-the-dialog-editor.md)  
  
-   [대화 상자 편집기 문제 해결](../windows/troubleshooting-the-dialog-editor.md)  
  
    > [!TIP]
    >  대부분 대화 상자 편집기를 사용할 때 마우스 오른쪽 단추를 클릭하여 자주 사용하는 명령의 바로 가기 메뉴를 표시할 수 있습니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [리소스 편집기](../windows/resource-editors.md)   
 [컨트롤](../mfc/controls-mfc.md)   
 [컨트롤 클래스](../mfc/control-classes.md)   
 [대화 상자 클래스](../mfc/dialog-box-classes.md)   
 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)

