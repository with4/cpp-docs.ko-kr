---
title: "TN006: 메시지 맵 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.messages.maps
dev_langs:
- C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- ON_NOTIFY_RANGE macro [MFC]
- ON_COMMAND macro [MFC]
- ON_CONTROL_RANGE macro [MFC]
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_NOTIFY message [MFC]
- ON_COMMAND_RANGE_EX macro [MFC]
- ON_MESSAGE macro [MFC]
- Windows messages [MFC], message maps
- ON_COMMAND_RANGE macro [MFC]
- TN006
- ON_CONTROL macro [MFC]
- ON_COMMAND_EX macro [MFC]
- message maps [MFC], Windows messaging
ms.assetid: af4b6794-4b40-4f1e-ad41-603c3b7409bb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 567a44cd8d8b979a75eca7647861c579bf0c070b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn006-message-maps"></a>TN006: 메시지 맵
이 노트에서는 MFC 메시지 맵에 기능을 설명합니다.  
  
## <a name="the-problem"></a>문제  
 Microsoft Windows의 메시징 기능을 사용 하는 창 클래스에서 가상 함수를 구현 합니다. 관련 된 메시지의 수가 많아서 각 Windows 메시지에 대해 별도 가상 함수를 제공 하는 크지 vtable를 해지기 합니다.  
  
 Windows 시스템에서 정의한 메시지 수가 시간이 지남에 따라 변경 되 고 응용 프로그램에서 자신의 Windows 메시지를 정의할 수 있으므로 메시지 맵 때문에 인터페이스 변경 내용이 기존 코드를 수정 하지 않도록 설정 하는 간접 참조 수준을 제공 합니다.  
  
## <a name="overview"></a>개요  
 MFC는 창으로 전송 하는 메시지를 처리 하도록 기존의 Windows 기반 프로그램에서 사용 된 switch 문의에 대 한 대안을 제공 합니다. 메서드에 메시지에서의 매핑 적절 한 방법을 자동으로 호출 하 고 창에서 메시지를 받으면 되도록 정의할 수 있습니다. 이 메시지 맵 기능 가상 함수를 유사 하 게 만들어졌지만 가상 함수를 c + +로 나타낼 수 없는 추가 이점이 있습니다.  
  
## <a name="defining-a-message-map"></a>메시지 맵 정의  
 [DECLARE_MESSAGE_MAP](reference/message-map-macros-mfc.md#declare_message_map) 매크로 클래스에 대 한 세 가지 멤버를 선언 합니다.  
  
-   개인 배열 `AFX_MSGMAP_ENTRY` 라는 항목이 `_messageEntries`합니다.  
  
-   보호 된 `AFX_MSGMAP` 라는 구조 `messageMap` 가리키는 `_messageEntries` 배열입니다.  
  
-   보호 된 가상 함수 호출 `GetMessageMap` 의 주소를 반환 하는 `messageMap`합니다.  
  
 이 매크로 메시지 맵을 사용 하 여 모든 클래스의 선언에 넣어야 합니다. 규칙에 따라 클래스 선언의 끝입니다. 예:  
  
```  
class CMyWnd : public CMyParentWndClass  
{ *// my stuff...  
 
protected: *//{{AFX_MSG(CMyWnd)  
    afx_msg void OnPaint();
*//}}AFX_MSG  
 
    DECLARE_MESSAGE_MAP() 
};  
```  
  
 새 클래스를 만들 때 AppWizard 및 classwizard 함께 사용 하 여 생성 된 형식입니다. / / {{및 / /}} 클래스 마법사에 대 한 대괄호가 필요 합니다.  
  
 메시지 맵 테이블 집합이 한 메시지 맵 항목을 확장 하는 매크로 사용 하 여 정의 됩니다. 로 시작 하는 테이블 한 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) 이 메시지 맵에 의해 처리 되는 클래스와 처리 되지 않은 메시지 전달 되는 부모 클래스를 정의 하는 매크로 호출 합니다. 테이블 끝나는 [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) 매크로 호출 합니다.  
  
 이러한 두 매크로 호출 사이이 메시지 맵에 의해 처리 되는 각 메시지에 대 한 항목이입니다. 모든 표준 Windows 메시지에 ON_WM_ 폼의 매크로*MESSAGE_NAME* 해당 메시지에 대 한 항목을 생성 하는 합니다.  
  
 각 Windows 메시지의 매개 변수의 압축을 푼 고 형식 안전성을 제공 하기 위한 표준 함수 서명에 정의 되었습니다. 이러한 서명을 선언에 Afxwin.h 파일에서 찾을 수 있습니다의 [CWnd](../mfc/reference/cwnd-class.md)합니다. 키워드와 함께 각 하나의으로 표시 된 `afx_msg` 쉽게 식별 하기 위해 합니다.  
  
> [!NOTE]
>  클래스 마법사에서는 사용 해야 합니다는 `afx_msg` 메시지 맵 처리기 선언에서 키워드입니다.  
  
 이러한 함수 서명 된 간단한 규칙을 사용 하 여 파생 됩니다. 항상 함수의 이름으로 시작 `"On`"입니다. 다음 제거 "WM_" 인 Windows 메시지의 이름과 대문자로 된 각 단어의 첫 번째 문자입니다. 매개 변수 순서는 `wParam` 이어서 `LOWORD`(`lParam`) 다음 `HIWORD`(`lParam`). 사용 되지 않는 매개 변수가 전달 되지 않습니다. MFC 클래스에 의해 래핑된 핸들을 모두 적절 한 MFC 개체에 대 한 포인터 변환 됩니다. 다음 예제에서는 처리 하는 방법을 보여 줍니다.는 `WM_PAINT` 메시지 보내기 및 인해는 `CMyWnd::OnPaint` 함수를 호출할 수:  
  
```  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass) *//{{AFX_MSG_MAP(CMyWnd)  
    ON_WM_PAINT() *//}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 메시지 맵 테이블은 모든 함수 또는 클래스 정의의 범위를 벗어나는 정의 되어야 합니다. Extern "C" 블록에 저장 하지 마십시오.  
  
> [!NOTE]
>  클래스 마법사 간에 발생 하는 메시지 맵 항목을 수정 하는 / / {{및 / /}을 (를) 주석 대괄호입니다.  
  
## <a name="user-defined-windows-messages"></a>사용자 정의 Windows 메시지  
 사용자 정의 메시지를 사용 하 여 메시지 맵에 포함 될 수 있습니다는 [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) 매크로입니다. 이 매크로 메시지 번호와 폼의 메서드를 허용합니다.  
  
' ' * / / 클래스 선언 안에  
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

 
 #<a name="define-wmmymessage-wmuser--100"></a>WM_MYMESSAGE 정의 (WM_USER 100 +)  
 
BEGIN_MESSAGE_MAP (CMyWnd, CMyParentWndClass)  
    ON_MESSAGE (WM_MYMESSAGE, OnMyMessage)  
END_MESSAGE_MAP()  
```  
  
 In this example, we establish a handler for a custom message that has a Windows message ID derived from the standard `WM_USER` base for user-defined messages. The following example shows how to call this handler:  
  
```  
CWnd pWnd =...;  
pWnd SendMessage(WM_MYMESSAGE);->
```  
  
 The range of user-defined messages that use this approach must be in the range `WM_USER` to 0x7fff.  
  
> [!NOTE]
>  ClassWizard does not support entering `ON_MESSAGE` handler routines from the ClassWizard user interface. You must manually enter them from the Visual C++ editor. ClassWizard will parse these entries and let you browse them just like any other message-map entries.  
  
## Registered Windows Messages  
 The [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) function is used to define a new window message that is guaranteed to be unique throughout the system. The macro `ON_REGISTERED_MESSAGE` is used to handle these messages. This macro accepts a name of a `UINT NEAR` variable that contains the registered windows message ID. For example  
  
```  
CMyWnd 클래스: 공용 CMyParentWndClass  
{  
public:  
    CMyWnd();

 *//{{AFX_MSG(CMyWnd)  
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam); * //}}AFX_MSG  
 
    DECLARE_MESSAGE_MAP() 
};  
 
정적 UINT 근처 WM_FIND RegisterWindowMessage("COMMDLG_FIND"); =

 
BEGIN_MESSAGE_MAP (CMyWnd, CMyParentWndClass) *//{{AFX_MSG_MAP(CMyWnd)  
    ON_REGISTERED_MESSAGE (WM_FIND, OnFind) * //}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 The registered Windows message ID variable (WM_FIND in this example) must be a `NEAR` variable because of the way `ON_REGISTERED_MESSAGE` is implemented.  
  
 The range of user-defined messages that use this approach will be in the range 0xC000 to 0xFFFF.  
  
> [!NOTE]
>  ClassWizard does not support entering `ON_REGISTERED_MESSAGE` handler routines from the ClassWizard user interface. You must manually enter them from the text editor. ClassWizard will parse these entries and let you browse them just like any other message-map entries.  
  
## Command Messages  
 Command messages from menus and accelerators are handled in message maps with the `ON_COMMAND` macro. This macro accepts a command ID and a method. Only the specific `WM_COMMAND` message that has a `wParam` equal to the specified command ID is handled by the method specified in the message-map entry. Command handler member functions take no parameters and return `void`. The macro has the following form:  
  
```  
ON_COMMAND (id, memberFxn)  
```  
  
 Command update messages are routed through the same mechanism, but use the `ON_UPDATE_COMMAND_UI` macro instead. Command update handler member functions take a single parameter, a pointer to a [CCmdUI](../mfc/reference/ccmdui-class.md) object, and return `void`. The macro has the form  
  
```  
ON_UPDATE_COMMAND_UI (id, memberFxn)  
```  
  
 Advanced users can use the `ON_COMMAND_EX` macro, which is an extended form of command message handlers. The macro provides a superset of the `ON_COMMAND` functionality. Extended command-handler member functions take a single parameter, a `UINT` that contains the command ID, and return a `BOOL`. The return value should be `TRUE` to indicate that the command has been handled. Otherwise routing will continue to other command target objects.  
  
 Examples of these forms:  
  
-   Inside Resource.h (usually generated by Visual C++)  
  
 ```  
 #<a name="define----idmycmd------100"></a>ID_MYCMD 100 정의  
 #<a name="define----idcomplex----101"></a>ID_COMPLEX 101 정의  
 ```  
  
-   Inside the class declaration  
  
 ```  
    afx_msg void OnMyCommand();
afx_msg void OnUpdateMyCommand (CCmdUI * pCmdUI);

    afx_msg BOOL OnComplexCommand(UINT nID);

 ```  
  
-   Inside the message map definition  
  
 ```  
    ON_COMMAND(ID_MYCMD,
    OnMyCommand)  
    ON_UPDATE_COMMAND_UI(ID_MYCMD,
    OnUpdateMyCommand)  
    ON_COMMAND_EX(ID_MYCMD,
    OnComplexCommand)  
 ```  
  
-   In the implementation file  
  
 ```  
    void CMyClass::OnMyCommand()  
 {* / 명령을 처리 /  
 }  
 
    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)  
 {* / / pCmdUI와 UI 상태를 설정 합니다.  
 }  
 
    BOOL CMyClass::OnComplexCommand(UINT nID)  
 {* / 명령을 처리 /  
    TRUE를 반환 합니다.  
 }  
 ```  
  
 Advanced users can handle a range of commands by using a single command handler: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) or `ON_COMMAND_RANGE_EX`. See the product documentation for more information about these macros.  
  
> [!NOTE]
>  ClassWizard supports creating `ON_COMMAND` and `ON_UPDATE_COMMAND_UI` handlers, but it does not support creating `ON_COMMAND_EX` or `ON_COMMAND_RANGE` handlers. However, Class Wizard will parse and let you browse all four command handler variants.  
  
## Control Notification Messages  
 Messages that are sent from child controls to a window have an extra bit of information in their message map entry: the control's ID. The message handler specified in a message map entry is called only if the following conditions are true:  
  
-   The control notification code (high word of `lParam`), such as BN_CLICKED, matches the notification code specified in the message-map entry.  
  
-   The control ID (`wParam`) matches the control ID specified in the message-map entry.  
  
 Custom control notification messages may use the [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) macro to define a message map entry with a custom notification code. This macro has the form  
  
```  
ON_CONTROL (wNotificationCode, id, memberFxn)  
```  
  
 For advanced usage [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) can be used to handle a specific control notification from a range of controls with the same handler.  
  
> [!NOTE]
>  ClassWizard does not support creating an `ON_CONTROL` or `ON_CONTROL_RANGE` handler in the user interface. You must manually enter them with the text editor. ClassWizard will parse these entries and let you browse them just like any other message map entries.  
  
 The Windows Common Controls use the more powerful [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) for complex control notifications. This version of MFC has direct support for this new message by using the `ON_NOTIFY` and `ON_NOTIFY_RANGE` macros. See the product documentation for more information about these macros.  
  
## See Also  
 [Technical Notes by Number](../mfc/technical-notes-by-number.md)   
 [Technical Notes by Category](../mfc/technical-notes-by-category.md)

