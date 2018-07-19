---
title: 'TN061: ON_NOTIFY 및 WM_NOTIFY 메시지 | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs:
- C++
helpviewer_keywords:
- ON_NOTIFY_EX message [MFC]
- TN061
- ON_NOTIFY message [MFC]
- ON_NOTIFY_EX_RANGE message [MFC]
- ON_NOTIFY_RANGE message [MFC]
- notification messages
- WM_NOTIFY message
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74b5a6a8d072a0cea9c92b9766fbe3ffa7c84c4f
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122512"
---
# <a name="tn061-onnotify-and-wmnotify-messages"></a>TN061: ON_NOTIFY 및 WM_NOTIFY 메시지

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 기술 노트 새 WM_NOTIFY 메시지에 대 한 배경 정보를 제공 하 고는 권장 하 고 가장 일반적인 방법은 MFC 응용 프로그램에서 WM_NOTIFY 메시지 처리를 설명 합니다.

**Windows에서 알림 메시지 3.x**

Windows에서 3.x에서 부모에 메시지를 전송 하 여 콘텐츠 및 선택 및 제어 배경 그림에서 변경 컨트롤 예: 마우스 클릭 이벤트의 부모에 게 알림입니다. 간단한 알림 (예: BN_CLICKED) 알림 코드와 특수 WM_COMMAND 메시지로 전송 및 ID에 압축을 제어할 *wParam* 및에서 컨트롤의 핸들이 *lParam*합니다. 이후에 *wParam* 및 *lParam* 는 추가 데이터를 전달할 수 없으므로 전체-이 메시지에만 간단한 알림이 될 수 있습니다. 예를 들어, BN_CLICKED 알림 있어서 단추 클릭 했을 때 마우스 커서의 위치에 대 한 정보를 보낼 수 없습니다.

다양 한 특수 한 용도의 메시지를 WM_CTLCOLOR, WM_VSCROLL, WM_HSCROLL, WM_DRAWITEM, WM_MEASUREITEM, WM_COMPAREITEM, WM_DELETEITEM, WM_ 3.x를 해야 하는 Windows에 컨트롤 추가 데이터를 포함 하는 알림 메시지를 보내면 사용 CHARTOITEM, WM_VKEYTOITEM, 및 등입니다. 이러한 메시지는 다시 보낸 컨트롤에 반영 될 수 있습니다. 자세한 내용은 참조 [TN062: Windows 컨트롤에 대 한 메시지 리플렉션](../mfc/tn062-message-reflection-for-windows-controls.md)합니다.

**Win32에서 알림 메시지**

Windows 3.1에 존재 하는 컨트롤에 대 한 Win32 API의에서 사용 하 여 사용 된 알림 메시지의 대부분 Windows 3.x 합니다. 그러나 Win32에도 추가 여러 정교 하 고 복잡 한 컨트롤 창에서 지 원하는 3.x 합니다. 대부분의 경우 이러한 컨트롤의 알림 메시지를 사용 하 여 추가 데이터를 전송 해야 합니다. 새 추가 하는 대신 **WM_\***  추가 데이터를 Win32 API의 디자이너는 각 새로운 알림이 하나만 메시지, 모든 시간에 추가 데이터를 전달할 수 있는 WM_NOTIFY 추가 하기로 선택에 대 한 메시지는 표준화 된 방식으로 합니다.

WM_NOTIFY 메시지 메시지를 전송 하는 컨트롤의 ID를 포함 *wParam* 및 구조에 대 한 포인터 *lParam*합니다. 이 구조는 하나는 **NMHDR** 구조 또는 일부 큰 구조체는 **NMHDR** 첫 번째 멤버로 구조입니다. 이후에는 **NMHDR** 멤버는 첫 번째에 대 한 포인터와이 구조에 대 한 포인터를 사용할 수 있습니다는 **NMHDR** 또는 다른 이름으로 캐스팅 한 방법에 따라 더 큰 구조에 대 한 포인터입니다.

대부분의 경우에서 포인터는 큰 구조체를 가리킵니다 및 사용할 때 캐스팅 해야 합니다. 일반적인 알림과 같은 몇 가지 알림에 (이름의 시작 **NM_**) 및 도구 컨트롤의 TTN_SHOW 및 TTN_POP 알림을 팁,이 **NMHDR** 실제로 사용 되는 구조입니다.

**NMHDR** 구조 또는 초기 구성원 핸들 및 메시지와 알림 코드 (예: TTN_SHOW)를 전송 하는 컨트롤의 ID를 포함 합니다. 형식은 **NMHDR** 구조는 다음과 같습니다.

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;
    UINT idFrom;
    UINT code;
} NMHDR;
```

TTN_SHOW 메시지에 대 한는 **코드** 멤버 TTN_SHOW로 설정 됩니다.

대부분의 공지 포인터를 포함 하는 큰 구조를 전달는 **NMHDR** 첫 번째 멤버로 구조입니다. 예를 들어 목록 뷰 컨트롤에서 키를 누를 때 전송 되는 목록 뷰 컨트롤의 LVN_KEYDOWN 알림 메시지에 의해 사용 되는 구조입니다. 가리키는 포인터는 **LV_KEYDOWN** 구조를 아래 표시 된 것과 같이 정의 됩니다.

```cpp
typedef struct tagLV_KEYDOWN {
    NMHDR hdr;
    WORD wVKey;
    UINT flags;
} LV_KEYDOWN;
```

이후에는 **NMHDR** 멤버는이 구조에서 첫 번째, 알림 메시지에 전달 하는 포인터에 대 한 포인터로 캐스팅 될 수는 **NMHDR** 또는에 대 한 포인터는 **LV_KEYDOWN** .

**모든 새 Windows 컨트롤에 공통 된 알림**

일부 알림은 모든 새 Windows 컨트롤에 공통적으로 적용 합니다. 이러한 알림을 전달에 대 한 포인터는 **NMHDR** 구조입니다.

|알림 코드|전송 하기 때문에|
|-----------------------|------------------|
|NM_CLICK|사용자는 컨트롤에서 마우스 왼쪽된 단추를 클릭 했습니다.|
|NM_DBLCLK|컨트롤의 사용자 두 번 클릭된 마우스 왼쪽된 단추|
|NM_RCLICK|사용자가 컨트롤을 마우스 오른쪽 단추로 클릭 한|
|NM_RDBLCLK|컨트롤의 사용자 두 번 클릭된 마우스 오른쪽 단추|
|NM_RETURN|사용자는 컨트롤에 입력 포커스가 있는 동안 ENTER 키를 눌렀습니다.|
|NM_SETFOCUS|컨트롤에 입력된 포커스가 지정|
|NM_KILLFOCUS|컨트롤에 입력된 포커스가 손실 되었습니다.|
|NM_OUTOFMEMORY|없기 때문에 메모리가 부족 하 여 사용 가능한 컨트롤이는 작업을 완료할 수 없습니다.|

##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> ON_NOTIFY: MFC 응용 프로그램에서 WM_NOTIFY 메시지를 처리합니다.

함수 `CWnd::OnNotify` 알림 메시지를 처리 합니다. 기본 구현에 알림 처리기를 호출에 대 한 메시지 맵을 확인 합니다. 재정의 하지 않으면 일반적으로 `OnNotify`합니다. 대신, 처리기 함수를 제공 하 고 해당 처리기에 대 한 메시지 맵 항목을 소유자 창 클래스의 메시지 맵에 추가 합니다.

클래스 마법사 클래스 마법사 속성 시트를 통해 ON_NOTIFY 메시지-맵 항목을 만들 수 있으며 기본 처리기 함수를 제공 됩니다. 클래스 마법사를 사용 하 여 쉽게이에 대 한 자세한 내용은 참조 하십시오. [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)합니다.

ON_NOTIFY 메시지 맵 매크로는 다음 구문을 가집니다.

```cpp
ON_NOTIFY(wNotifyCode, id, memberFxn)
```

여기서 매개 변수는 다음과 같습니다.

*wNotifyCode*  
 LVN_KEYDOWN 등을 처리 하는 알림 메시지에 대 한 코드입니다.

*ID*  
 알림이 전송 된 컨트롤의 자식 식별자입니다.

*memberFxn*  
 이 알림이 전송 되 면 호출 되는 멤버 함수입니다.

멤버 함수는 다음과 같은 프로토타입으로 선언 해야 합니다.

```cpp
afx_msg void memberFxn(NMHDR* pNotifyStruct, LRESULT* result);
```

여기서 매개 변수는 다음과 같습니다.

*pNotifyStruct*  
 위의 섹션에 설명 된 대로 알림 구조에 대 한 포인터입니다.

*결과*  
 결과 코드에 대 한 포인터를 반환 하기 전에 설정 합니다.

## <a name="example"></a>예

멤버 함수를 지정 하려면 `OnKeydownList1` LVN_KEYDOWN 메시지를 처리 하는 `CListCtrl` ID가 갖는 `IDC_LIST1`을 메시지 맵에 다음을 추가 하 여 클래스 마법사를 사용 하면:

```cpp
ON_NOTIFY(LVN_KEYDOWN, IDC_LIST1, OnKeydownList1)
```

위의 예에서 클래스 마법사에서 제공 하는 함수가입니다.

```cpp
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)
{
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;
    
    // TODO: Add your control notification handler
    //       code here

    *pResult = 0;
}
```

참고 클래스 마법사 적절 한 형식의 포인터를 자동으로 제공 합니다. 알림 구조 중 하나를 통해 액세스할 수 *pNMHDR* 또는 *pLVKeyDow*합니다.

##  <a name="_mfcnotes_on_notify_range"></a> ON_NOTIFY_RANGE

컨트롤의 집합에 대 한 동일한 WM_NOTIFY 메시지를 처리 해야 할 경우 ON_NOTIFY 보다는 ON_NOTIFY_RANGE를 사용할 수 있습니다. 예를 들어, 특정 알림 메시지에 대 한 같은 작업을 수행 하려는 단추 집합을 할 수 있습니다.

ON_NOTIFY_RANGE를 사용 하면 연속 된 범위의 시작을 지정 하 고 자식 식별자의 범위를 종료 하 여 알림 메시지를 처리 하려는 자식 식별자를 지정 합니다.

클래스 마법사 ON_NOTIFY_RANGE; 처리 하지 않습니다. 를 사용 하려면 메시지 맵에 직접 편집 해야 합니다.

메시지 맵 항목 및 ON_NOTIFY_RANGE 함수 프로토타입에 다음과 같습니다.

```cpp
ON_NOTIFY_RANGE(wNotifyCode, id, idLast, memberFxn)
```

여기서 매개 변수는 다음과 같습니다.

*wNotifyCode*  
 LVN_KEYDOWN 등을 처리 하는 알림 메시지에 대 한 코드입니다.

*ID*  
 식별자의 연속 된 범위에서 첫 번째 식별자입니다.

*idLast*  
 식별자의 연속 된 범위에서 마지막 식별자입니다.

*memberFxn*  
 이 알림이 전송 되 면 호출 되는 멤버 함수입니다.

멤버 함수는 다음과 같은 프로토타입으로 선언 해야 합니다.

```cpp
afx_msg void memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

여기서 매개 변수는 다음과 같습니다.

*ID*  
 알림을 전송 하는 컨트롤의 자식 식별자입니다.

*pNotifyStruct*  
 위에서 설명한 것 처럼 알림 구조에 대 한 포인터입니다.

*결과*  
 결과 코드에 대 한 포인터를 반환 하기 전에 설정 합니다.

##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON_NOTIFY_EX, ON_NOTIFY_EX_RANGE

메시지를 처리 하도록 라우팅 알림 영역에서 둘 이상의 개체를 원하는 경우 ON_NOTIFY (또는 ON_NOTIFY_RANGE) 하는 대신 ON_NOTIFY_EX (또는 ON_NOTIFY_EX_RANGE)를 사용할 수 있습니다. 간의 유일한 차이점은 **EX** 버전과 일반 버전은 멤버 함수에 대 한 호출 되도록는 **EX** 버전 반환는 **BOOL** 나타내는 여부 메시지 처리를 계속 합니다. 반환 **FALSE** 이 함수에서 둘 이상의 개체에 동일한 메시지를 처리할 수 있습니다.

ON_NOTIFY_EX 또는 ON_NOTIFY_EX_RANGE; classwizard 함께 사용을 처리 하지 않습니다. 그 중 하나를 사용 하려는 경우 메시지 맵에 직접 편집 해야 합니다.

메시지 맵 항목 및 ON_NOTIFY_EX 및 ON_NOTIFY_EX_RANGE 함수 프로토타입에 다음과 같습니다. 매개 변수의 의미는 이외의 경우와 동일**EX** 버전입니다.

```cpp
ON_NOTIFY_EX(nCode, id, memberFxn)
ON_NOTIFY_EX_RANGE(wNotifyCode, id, idLast, memberFxn)
```

위의 두 항목 모두에 대 한 프로토타입의 같습니다.

```cpp
afx_msg BOOL memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

두 경우 모두 *id* 알림을 전송 하는 컨트롤의 자식 식별자를 포함 합니다.

함수 반환 해야 **TRUE** 알림 메시지를 완전히 처리 된 경우 또는 **FALSE** 명령 라우팅의 다른 개체에 메시지를 처리 하는 경우 되어 있어야 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)  
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)  
