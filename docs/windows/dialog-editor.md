---
title: 대화 상자 편집기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
dev_langs:
- C++
helpviewer_keywords:
- resource editors, Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes, editing
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c2f5339237bec053df6bf26fb161854f83f572a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651852"
---
# <a name="dialog-editor"></a>대화 상자 편집기
합니다 **대화 상자** 편집기를 만들거나 대화 상자 리소스를 편집할 수 있습니다. 대화 상자의.rc 파일에서 두 번 클릭 하 여 대화 상자 편집기를 열면 합니다 **리소스 뷰** 창 (**뷰** > **리소스 뷰**). 사실은 **리소스 뷰** 를 Express 버전에서는 사용할 수 없습니다.  
  
 새 대화 상자(또는 대화 상자 템플릿)를 만드는 첫 번째 단계 중 하나는 대화 상자에 컨트롤을 추가하는 것입니다. 에 **대화 상자** 편집기는 특정 크기, 모양 또는 맞춤에 맞게 컨트롤을 정렬할 수 있습니다 또는 대화 상자에서 작업 하기 위한 해결 방법은 이동할 수 있습니다. 또한 컨트롤을 쉽게 삭제할 수 있습니다.  
  
 대화 상자를 템플릿으로 저장하여 다시 사용할 수 있습니다. 대화 상자 디자인과 이를 구현하는 코드 편집 간을 쉽게 전환할 수도 있습니다.  
  
 대화 상자 편집기에서 단일 또는 여러 컨트롤의 속성을 편집할 수도 있습니다. 탭 순서를 변경할 수 있습니다, 컨트롤에 대 한 나타나는 순서 즉, 포커스를 **탭** 키를 누르면 또는 키보드를 사용 하 여 컨트롤을 선택할 수 있게 해 주는 액세스 키 (키 조합)을 정의할 수 있습니다. 미리 설정된 액세스 키 목록은 [대화 상자 편집기의 액셀러레이터 키](../windows/accelerator-keys-for-the-dialog-editor.md)를 참조하세요.  
  
 합니다 **대화 상자** 편집기에서는 ActiveX 컨트롤을 포함 하 여 사용자 지정 컨트롤을 사용할 수 있습니다. 또한 [폼 보기](../mfc/reference/cformview-class.md), [레코드 뷰](../data/record-views-mfc-data-access.md)또는 [대화 상자 모음](../mfc/dialog-bars.md)을 편집할 수 있습니다.  
  
 Visual Studio 2015부터 컨트롤의 이동 및 사용자가 대화 상자 크기 조정의 크기를 조정 하는 방법을 지정 하는 동적 레이아웃을 정의 하려면 대화 상자 편집기를 사용할 수 있습니다. 자세한 내용은 [Dynamic Layout](../mfc/dynamic-layout.md)을 참조하세요.  
  
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
    >  사용 하는 동안 합니다 **대화 상자** 편집기, 대부분의 경우 자주 사용 되는 명령의 바로 가기 메뉴를 표시 하려면 마우스 오른쪽 단추 클릭 수 있습니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [리소스 편집기](../windows/resource-editors.md)   
 [컨트롤](../mfc/controls-mfc.md)   
 [컨트롤 클래스](../mfc/control-classes.md)   
 [대화 상자 클래스](../mfc/dialog-box-classes.md)   
 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)