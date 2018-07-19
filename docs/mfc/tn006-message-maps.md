---
title: 'TN006: 메시지 맵 | Microsoft Docs'
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c4bc820c6b54e055235c1bd29bd55ccfc032c92
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121678"
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

- AFX_MSGMAP_ENTRY 항목의 개인 배열 호출 *_messageEntries*합니다.

- 보호 된 AFX_MSGMAP 구조 호출 *messageMap* 가리키는 *_messageEntries* 배열입니다.

- 보호 된 가상 함수 호출 `GetMessageMap` 의 주소를 반환 하는 *messageMap*합니다.

이 매크로 메시지 맵을 사용 하 여 모든 클래스의 선언에 넣어야 합니다. 규칙에 따라 클래스 선언의 끝입니다. 예:

```cpp
class CMyWnd : public CMyParentWndClass
{
    // my stuff...

protected:
    //{{AFX_MSG(CMyWnd)
    afx_msg void OnPaint();
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};
```

새 클래스를 만들 때 AppWizard 및 classwizard 함께 사용 하 여 생성 된 형식입니다. / / {{및 / /}} 클래스 마법사에 대 한 대괄호가 필요 합니다.

메시지 맵 테이블 집합이 한 메시지 맵 항목을 확장 하는 매크로 사용 하 여 정의 됩니다. 로 시작 하는 테이블 한 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) 이 메시지 맵에 의해 처리 되는 클래스와 처리 되지 않은 메시지 전달 되는 부모 클래스를 정의 하는 매크로 호출 합니다. 테이블 끝나는 [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) 매크로 호출 합니다.

이러한 두 매크로 호출 사이이 메시지 맵에 의해 처리 되는 각 메시지에 대 한 항목이입니다. 모든 표준 Windows 메시지에 ON_WM_ 폼의 매크로*MESSAGE_NAME* 해당 메시지에 대 한 항목을 생성 하는 합니다.

각 Windows 메시지의 매개 변수의 압축을 푼 고 형식 안전성을 제공 하기 위한 표준 함수 서명에 정의 되었습니다. 이러한 서명을 선언에 Afxwin.h 파일에서 찾을 수 있습니다의 [CWnd](../mfc/reference/cwnd-class.md)합니다. 키워드와 함께 각 하나의으로 표시 된 **afx_msg** 쉽게 식별 하기 위해 합니다.

> [!NOTE]
> 클래스 마법사에서는 사용 해야 합니다는 **afx_msg** 메시지 맵 처리기 선언에서 키워드입니다.

 이러한 함수 서명 된 간단한 규칙을 사용 하 여 파생 됩니다. 항상 함수의 이름으로 시작 `"On`"입니다. 다음 제거 "WM_" 인 Windows 메시지의 이름과 대문자로 된 각 단어의 첫 번째 문자입니다. 매개 변수 순서는 *wParam* 이어서 `LOWORD`(*lParam*) 다음 `HIWORD`(*lParam*). 사용 되지 않는 매개 변수가 전달 되지 않습니다. MFC 클래스에 의해 래핑된 핸들을 모두 적절 한 MFC 개체에 대 한 포인터 변환 됩니다. WM_PAINT 메시지를 처리 하는 방법을 보여 주는 다음 예제는 `CMyWnd::OnPaint` 함수를 호출할 수 있습니다.

```cpp
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_WM_PAINT()
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

 메시지 맵 테이블은 모든 함수 또는 클래스 정의의 범위를 벗어나는 정의 되어야 합니다. Extern "C" 블록에 저장 하지 마십시오.

> [!NOTE]
> 클래스 마법사 간에 발생 하는 메시지 맵 항목을 수정 하는 / / {{및 / /}을 (를) 주석 대괄호입니다.

## <a name="user-defined-windows-messages"></a>사용자 정의 Windows 메시지

사용자 정의 메시지를 사용 하 여 메시지 맵에 포함 될 수 있습니다는 [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) 매크로입니다. 이 매크로 메시지 번호와 폼의 메서드를 허용합니다.

```cpp
    // inside the class declaration
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

    #define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()
```

이 예제에서는 사용자 정의 메시지에 대 한 표준 WM_USER 기준에서 파생 된 Windows 메시지 ID를 포함 한 사용자 지정 메시지에 대 한 처리기를 설정 합니다. 다음 예제에서는이 처리기를 호출 하는 방법을 보여 줍니다.

```cpp
CWnd* pWnd = ...;
pWnd->SendMessage(WM_MYMESSAGE);
```

이 방법을 사용 하는 사용자 정의 메시지의 범위는 0x7fff WM_USER 범위에 있어야 합니다.

> [!NOTE]
> 클래스 마법사 클래스 마법사 사용자 인터페이스에서 입력 ON_MESSAGE 처리기 루틴을 지원 하지 않습니다. Visual c + + 편집기에서 수동으로 입력 해야 합니다. 클래스 마법사는 이러한 항목을 구문 분석 하 고 다른 메시지 맵 항목 처럼이 검색할 수 됩니다.

## <a name="registered-windows-messages"></a>등록 된 Windows 메시지

[RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) 함수는 시스템 전체에서 고유 하 게 보장 되는 새 창 메시지를 정의 하는 데 사용 됩니다. ON_REGISTERED_MESSAGE 매크로 사용 하 여 이러한 메시지를 처리 합니다. 이 매크로의 이름을 허용는 *UINT 근처* 등록 된 windows 메시지 id입니다. 포함 된 변수 예

```cpp
class CMyWnd : public CMyParentWndClass
{
public:
    CMyWnd();

    //{{AFX_MSG(CMyWnd)
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam);
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};

static UINT NEAR WM_FIND = RegisterWindowMessage("COMMDLG_FIND");

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

등록 된 Windows 메시지 ID 변수 (이 예제의 WM_FIND) 이어야 합니다는 *NEAR* 방식 때문에 변수 ON_REGISTERED_MESSAGE 구현 됩니다.

이 방법을 사용 하는 사용자 정의 메시지의 0xC000에서 0xFFFF 범위에 오게 됩니다.

> [!NOTE]
> 클래스 마법사 클래스 마법사 사용자 인터페이스에서 입력 ON_REGISTERED_MESSAGE 처리기 루틴을 지원 하지 않습니다. 텍스트 편집기에서 수동으로 입력 해야 합니다. 클래스 마법사는 이러한 항목을 구문 분석 하 고 다른 메시지 맵 항목 처럼이 검색할 수 됩니다.

## <a name="command-messages"></a>명령 메시지

ON_COMMAND 매크로와 메시지 맵 명령 메시지 메뉴 및 액셀러레이터에서 처리 됩니다. 이 매크로 명령 ID와 메서드를 허용합니다. 만 특정 WM_COMMAND 포함 된 메시지를 한 *wParam* 같은 지정된 된 명령 ID는 메시지 맵 항목에 지정 된 메서드에서 처리 됩니다. 명령 처리기 멤버 함수 매개 변수가 없는 다음 다시 돌아와 **void**합니다. 매크로 형식은 다음과 같습니다.

```cpp
ON_COMMAND(id, memberFxn)
```

명령 업데이트 메시지는 동일한 메커니즘을 통해 라우팅됩니다 하지만 ON_UPDATE_COMMAND_UI 매크로 대신 사용 합니다. 단일 매개 변수에 대 한 포인터를 사용 하는 명령 업데이트 처리기 멤버 함수는 [CCmdUI](../mfc/reference/ccmdui-class.md) 개체를 반환할 **void**합니다. 매크로 형식은 다음과 같습니다.

```cpp
ON_UPDATE_COMMAND_UI(id, memberFxn)
```

고급 사용자는 명령 메시지 처리기의 확장 된 형태로 ON_COMMAND_EX 매크로 사용할 수 있습니다. 매크로는 ON_COMMAND 기능의 상위 집합을 제공합니다. 확장 된 명령 처리기 멤버 함수는 단일 매개 변수를 사용 합니다.는 **UINT** 명령 ID를 포함 하 고 반환 된 **BOOL**합니다. 반환 값 이어야 **TRUE** 명령 처리 된 것을 나타냅니다. 그렇지 않으면 라우팅 다른 명령 대상 개체에 계속 됩니다.

이러한 폼의 예:

- 내부 Resource.h (일반적으로 Visual c + +에서 생성)

    ```cpp
    #define    ID_MYCMD      100
    #define    ID_COMPLEX    101
    ```

- 클래스 선언 안에

    ```cpp
    afx_msg void OnMyCommand();
    afx_msg void OnUpdateMyCommand(CCmdUI* pCmdUI);
    afx_msg BOOL OnComplexCommand(UINT nID);
    ```

- 메시지 맵 정의 내부

    ```cpp
    ON_COMMAND(ID_MYCMD, OnMyCommand)
    ON_UPDATE_COMMAND_UI(ID_MYCMD, OnUpdateMyCommand)
    ON_COMMAND_EX(ID_MYCMD, OnComplexCommand)
    ```

- 구현 파일

    ```cpp
    void CMyClass::OnMyCommand()
    {
        // handle the command
    }

    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)
    {
        // set the UI state with pCmdUI
    }

    BOOL CMyClass::OnComplexCommand(UINT nID)
    {
        // handle the command
        return TRUE;
    }
    ```

 고급 사용자는 단일 명령 처리기를 사용 하 여 다양 한 명령 처리할 수 있습니다: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) 또는 ON_COMMAND_RANGE_EX 합니다. 이러한 매크로 대 한 자세한 내용은 제품 설명서를 참조 하십시오.

> [!NOTE]
> 클래스 마법사 만드는 ON_COMMAND 및 ON_UPDATE_COMMAND_UI 처리기를 지원 하지만 만드는 ON_COMMAND_EX 또는 ON_COMMAND_RANGE 처리기를 지원 하지 않습니다. 그러나 클래스 마법사는 구문 분석 하 고 모든 4 개의 명령 처리기 변형 탐색할 수 있도록 합니다.

## <a name="control-notification-messages"></a>컨트롤 알림 메시지

창에 자식 컨트롤에서 추가 비트가 정보 메시지에 전송 된 메시지 맵 항목: 컨트롤의 id입니다. 메시지 맵 항목에 지정 된 메시지 처리기는 다음 조건이 true 인 경우에 호출 됩니다.

- 컨트롤 알림 코드 (의 높은 단어 *lParam*), BN_CLICKED, 예: 메시지 맵 항목에 지정 된 알림 코드와 일치 합니다.

- 컨트롤 ID (*wParam*) 메시지 맵 항목에 지정 된 컨트롤 ID와 일치 합니다.

사용자 지정 컨트롤 알림 메시지를 사용할 수는 [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) 매크로를 사용자 지정 알림 코드로 메시지 맵 항목을 정의 합니다. 이 매크로 형식은 다음과 같습니다.

```cpp
ON_CONTROL(wNotificationCode, id, memberFxn)
```

고급 사용에 대 한 [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) 는 동일한 처리기를 사용 하 여 컨트롤의 범위에서 특정 컨트롤 알림 메시지를 처리 하는 데 사용할 수 있습니다.

> [!NOTE]
> 클래스 마법사 사용자 인터페이스에서 ON_CONTROL 또는 ON_CONTROL_RANGE 처리기 만들기를 지원 하지 않습니다. 텍스트 편집기에 직접 입력 해야 있습니다. 클래스 마법사는 이러한 항목을 구문 분석 하 고 다른 메시지 맵 항목 처럼이 검색할 수 됩니다.

Windows 공용 컨트롤 사용 보다 강력한 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) 복잡 한 제어 알림에 대 한 합니다. 이 버전의 MFC ON_NOTIFY 및 ON_NOTIFY_RANGE 매크로 사용 하 여이 새 메시지에 대 한 직접 지원을 있습니다. 이러한 매크로 대 한 자세한 내용은 제품 설명서를 참조 하십시오.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)  
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)  
