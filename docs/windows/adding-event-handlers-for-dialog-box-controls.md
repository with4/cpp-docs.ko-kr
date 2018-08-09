---
title: 대화 상자 컨트롤에 대 한 이벤트 처리기를 추가 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog editor, adding event handlers to controls
- controls [C++], event handlers
- dialog box controls, events
- event handlers, for dialog box controls
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2dce9b2ce59eb98c59c7a6cf04be52f3d439fdb0
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642853"
---
# <a name="adding-event-handlers-for-dialog-box-controls"></a>대화 상자 컨트롤에 사용할 이벤트 처리기 추가

이미 클래스와 연결 되어 있는 프로젝트 대화 상자에 대 한 이벤트 처리기를 만들 때 일부 바로 가기 키는 활용을 걸릴 수 있습니다. 기본 컨트롤 알림 이벤트 또는 적용 가능한 모든 Windows 메시지에 대 한 처리기를 신속 하 게 만들 수 있습니다.

### <a name="to-create-a-handler-for-the-default-control-notification-event"></a>기본 컨트롤 알림 이벤트에 대 한 처리기를 만들려면

1. 컨트롤을 두 번 클릭 합니다. 합니다 **텍스트** 편집기가 열립니다.

2. 에 컨트롤 알림 처리기 코드를 추가 합니다 **텍스트** 편집기입니다.

### <a name="to-create-a-handler-for-any-applicable-windows-message"></a>모든 적용 가능한 Windows 메시지에 대 한 처리기를 만들려면

1. 알림 이벤트를 처리 하려는 컨트롤을 클릭 합니다.

2. 에 [속성 창](/visualstudio/ide/reference/properties-window), 클릭는 **컨트롤 이벤트** 단추 컨트롤과 관련 된 일반적인 Windows 이벤트의 목록을 표시 합니다. 예를 들어 표준 **확인** 단추를 **에 대 한** 다음 알림 이벤트를 나열 하는 대화 상자:

   - BN_CLICKED

   - BN_DOUBLECLICKED

   - BN_KILLFOCUS

   - BN_SETFOCUS

    > [!NOTE]
    > 또는 대화 상자를 선택 하 고 클릭 합니다 **컨트롤 이벤트** 단추를 대화 상자에서 모든 컨트롤에 대 한 일반적인 Windows 이벤트의 목록을 표시 합니다.

3. 에 **속성** 창에서 이벤트를 처리 하기 위해 옆에 있는 오른쪽 열을 클릭 하 고 제안 된 알림 이벤트 이름을 선택 합니다 (예를 들어 `OnBnClickedOK` BN_CLICKED 처리).

    > [!NOTE]
    > 또는 기본 이벤트 처리기 이름을 선택 하는 것이 아니라 선택한 이벤트 처리기 이름을 제공할 수 있습니다.

   Visual Studio가 열리고 사용자가 이벤트를 선택 합니다 **텍스트 편집기** 이벤트 처리기의 코드를 표시 합니다. 예를 들어, 다음 코드는 기본 추가 `OnBnClickedOK`:

    ```cpp
    void CAboutDlg::OnBnClickedOk(void)
    {
        // TODO: Add your control notification handler code here
    }
    ```

추가할 이벤트 처리기 클래스 이외의 다른 대화 상자를 구현 하는 것을 사용 하려는 경우는 [이벤트 처리기 마법사](../ide/event-handler-wizard.md)합니다. 자세한 내용은 [이벤트 처리기를 추가](../ide/adding-an-event-handler-visual-cpp.md)합니다.

관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.

## <a name="requirements"></a>요구 사항
 Win32

## <a name="see-also"></a>참고 항목
 [기본 컨트롤 이벤트](../windows/default-control-events.md)  
 [대화 상자 컨트롤의 멤버 변수 정의](../windows/defining-member-variables-for-dialog-controls.md)  
 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)  
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)  
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)  
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)  
 [가상 함수 재정의](../ide/overriding-a-virtual-function-visual-cpp.md)  
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)  