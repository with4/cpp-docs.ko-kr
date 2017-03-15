---
title: "TN061: ON_NOTIFY 및 WM_NOTIFY 메시지 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_NOTIFY"
  - "WM_NOTIFY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "알림 메시지"
  - "ON_NOTIFY 메시지"
  - "ON_NOTIFY_EX 메시지"
  - "ON_NOTIFY_EX_RANGE 메시지"
  - "ON_NOTIFY_RANGE 메시지"
  - "TN061"
  - "WM_NOTIFY 메시지"
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN061: ON_NOTIFY 및 WM_NOTIFY 메시지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다.  따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다.  최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 기술 노트는 MFC 응용 프로그램에서 **WM\_NOTIFY** 메세지에 대한 배경 정보를 제공하고 **WM\_NOTIFY** 메세지 처리에 대한 추천 방법\(가장 일반적인\)을 설명합니다.  
  
 **Windows 3.x에서 알림 메세지**  
  
 Windows3.x 에서, 컨트롤은 콘텐츠 및 선택의 변경, 마우스 클릭, 부모에게 보내는 메세지에 의해 그려진 배경 컨트롤의 부모에게 알립니다.  간단한 알림은 알림 코드\(**BN\_CLICKED**와 같은\)와 `wParam` 로 압축된 컨트롤 ID를 사용한 특별한 **WM\_COMMAND** 메세지이고 `lParam`에서 컨트롤의 핸들입니다.  `wParam` 및 `lParam` 가 다 차면 추가적인 데이터를 전송할 방법이 없습니다. 이러한 메세지는 간단한 알림입니다.  예를 들어, **BN\_CLICKED** 알림에서는 버튼이 클릭 되었을 때 마우스 커서에 대한 위치 정보를 보낼 수 없습니다.  
  
 Windows 3.x 에서 컨트롤이 추가적인 데이터를 포함하는 알림 메시지를 보내는 것이 필요하면 다양한 특수 메세지를 사용합니다. : `WM_CTLCOLOR`, `WM_VSCROLL`, `WM_HSCROLL`, `WM_DRAWITEM`, `WM_MEASUREITEM`, `WM_COMPAREITEM`, `WM_DELETEITEM`, `WM_CHARTOITEM`, `WM_VKEYTOITEM` 등등  이러한 메시지는 보낸 컨트롤에 반영할 수 있습니다.  자세한 내용은 [TN062: Message Reflection for Windows Controls](../mfc/tn062-message-reflection-for-windows-controls.md) 를 참조하십시오.  
  
 **Win32에서 알림 메시지**  
  
 Windows 3.1의 컨트롤 에서 Win32 API는 Windows 3.x 에서 사용하는 대부분의 알림 메세지를 사용합니다.  그러나, Win32 역시 Windows 3.x에서 지원되는 정교하고 복잡한 컨트롤의 수를 추가합니다.  대부분의 경우, 이러한 컨트롤은 해당 알림 메세지를 사용하여 필요한 데이터를 보냅니다.  추가적인 데이터를 필요로 하는 새로운 알림의 각각에 대한 **WM\_\*** 를 추가하기 보다는, Win32 API 의 디자이너는 하나의 메세지 표준화된 방식으로 추가 데이터의 양을 전달 할 수 있는 **WM\_NOTIFY**를 추가합니다.  
  
 **WM\_NOTIFY** 메세지는 `wParam` 에 메세지를 보내는 컨트롤의 ID를 포함하고 `lParam` 에서 구조체를 가르킵니다.  이 구조는 **NMHDR** 구조체 또는 첫 번째 멤버로서 **NMHDR** 구조체를 가지는 큰 구조체입니다.  **NMHDR** 가 첫 번째인 경우, 이 구조체에 대한 포인터는 **NMHDR** 에 대한 포인터 또는 캐스팅 방법에 따라 더 큰 구조체에 대한 포인터로 사용될 수 있습니다.  
  
 대부분의 경우에서 포인터를 가장 큰 구조체를 가르켜야 하고, 그것을 사용할 때 캐스팅해야 합니다.  일반적인 알림과 같은\(**NM\_** 로 시작하는\) 몇개의 알림과 도구 설명 컨트롤의 **TTN\_SHOW** 및 **TTN\_POP** 알림은 실제로 사용되는 **NMHDR** 구조체입니다.  
  
 **NMHDR** 구조체 또는 초기 멤버는 메세지와 알림 코드\(**TTN\_SHOW**와 같은\)를 보내는 핸들과 컨트롤의 ID를 포함합니다.  **NMHDR** 구조체의 형식은 아래와 같습니다 :  
  
```  
typedef struct tagNMHDR {  
    HWND hwndFrom;  
    UINT idFrom;  
    UINT code;  
} NMHDR;  
```  
  
 **TTN\_SHOW** 메세지에 대해, **code** 멤버는 **TTN\_SHOW** 로 설정됩니다.  
  
 대부분의 알림은 포인터를 첫 번째 멤버로 **NMHDR** 구조체를 포함하는 가장 큰 구조체에 전달합니다.  예를 들어, 리스트 뷰 컨트롤에 있는 키가 눌러졌을 때 전송되는 리스트 뷰 컨트롤의 **LVN\_KEYDOWN** 알림 메세지가 사용하는 구조체를 고려해야 합니다.  포인터가 가리키는 있는 **LV\_KEYDOWN** 구조체는 아래와 같이 정의 됩니다:  
  
```  
typedef struct tagLV_KEYDOWN {  
    NMHDR hdr;     
    WORD wVKey;    
    UINT flags;    
} LV_KEYDOWN;  
```  
  
 **NMHDR** 멤버가 이 구조체에서 첫 번째일 때, 알림 메세지로 전달된 포인터는 **NMHDR** 에 대한 포인터 또는 **LV\_KEYDOWN** 에 대한 포인터에 캐스팅 될 수 있습니다.  
  
 **모든 새 Windows 컨트롤에 대한 공통 알림**  
  
 일부 알림은 새 Windows 컨트롤의 모든 항목에 공통입니다.  이러한 알림은**NMHDR** 구조체에 포인터를 전달합니다.  
  
|알림 코드|때문에 전송합니다.|  
|-----------|----------------|  
|**NM\_CLICK**|사용자는 컨트롤에서 마우스 왼쪽 단추를 클릭합니다.|  
|**NM\_DBLCLK**|사용자는 컨트롤에서 마우스 왼쪽 단추를 더블 클릭합니다.|  
|**NM\_RCLICK**|사용자는 컨트롤에서 마우스 오른쪽 단추를 클릭합니다.|  
|**NM\_RDBLCLK**|사용자는 컨트롤에서 마우스 오른쪽 단추를 더블 클릭합니다.|  
|**NM\_RETURN**|컨트롤에 입력 포커스가 있을때 사용자가 ENTER 키를 눌렀습니다.|  
|**NM\_SETFOCUS**|컨트롤에 입력 포커스가 부여됩니다.|  
|**NM\_KILLFOCUS**|컨트롤이 입력 포커스를 잃습니다.|  
|**NM\_OUTOFMEMORY**|작업 메모리가 부족하여 컨트롤이 작업을 완료할 수 없습니다.|  
  
##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> ON\_NOTIFY: Handling WM\_NOTIFY Messages in MFC Applications  
 `CWnd::OnNotify` 함수는 알림 메세지를 처리합니다.  해당 기본 구현은 알림 처리기에 대해 호출에 대한 메세지 맵을 확인합니다.  일반적으로 `OnNotify` 는 재정의하지 않습니다.  대신 처리기 함수를 제공하고 소유자 창의 클래스의 메세지 맵에 대한 처리기에 대한 메세지 맵 엔트리를 추가합니다.  
  
 클래스 마법사 속성 시트를 통해 클래스 마법사는 `ON_NOTIFY` 메세지 맵 엔트리를 생성하고 기초 처리 함수를 제공합니다.  클래스 마법사를 쉽게 사용하는 방법에 대한 자세한 내용은 [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md) 를 참조하십시오.  
  
 `ON_NOTIFY` 메시지 맵 매크로는 아래의 문법을 가집니다.  
  
```  
  
ON_NOTIFY( wNotifyCode, id, memberFxn )  
```  
  
 기울임꼴로 표시 된 매개 변수로 대체 됩니다.  
  
 `wNotifyCode`  
 알림 메세지의 코드는 **LVN\_KEYDOWN** 와 같이 처리됩니다.  
  
 `id`  
 보내진 알림에 대한 컨트롤의 자식 식별자입니다.  
  
 `memberFxn`  
 이 알림이 전송될 때 호출되는 멤버 함수입니다.  
  
 멤버 함수는 다음과 같은 프로토타입을 사용 하여 선언 해야 합니다.  
  
```  
  
afx_msg void memberFxn( NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## 설명  
 여기서 기울임꼴 매개 변수는 다음과 같습니다.  
  
 `pNotifyStruct`  
 위 섹션에서 설명한 것 처럼 알림 구조에 대한 포인터입니다.  
  
 *result*  
 반환하기 전에 설정한 결과 코드에 대한 포인터입니다.  
  
## 예제  
 `IDC_LIST1` 가 ID 인 `CListCtrl` 에서 **LVN\_KEYDOWN** 메세지를 처리하기 위해 필요한 `OnKeydownList1` 함수를 지정하기 위해 클래스 마법사를 사용하여 메세지 맵에 다음을 추가하십시오.  
  
```  
ON_NOTIFY( LVN_KEYDOWN, IDC_LIST1, OnKeydownList1 )  
```  
  
 위의 예제에서, 함수는 클래스 마법사에서 제공하는 것입니다.  
  
```  
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)  
{  
   LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;  
   // TODO: Add your control notification handler  
   //       code here  
  
   *pResult = 0;  
}  
```  
  
 클래스 마법사는 올바른 형식의 포인터를 자동으로 제공합니다.  `pNMHDR` 또는 `pLVKeyDow` 를 통해 알림 구조체에 접근할 수 있습니다.  
  
##  <a name="_mfcnotes_on_notify_range"></a> ON\_NOTIFY\_RANGE  
 컨트롤의 집합에 대해 같은 **WM\_NOTIFY** 메세지를 처리해야 하는 경우, `ON_NOTIFY` 보다 **ON\_NOTIFY\_RANGE** 를 사용하십시오.  예를 들어, 알림 메시지에 대해 동일한 작업을 수행 하려면 단추 집합이 있어야 합니다.  
  
 **ON\_NOTIFY\_RANGE** 를 사용할 때, 연속 된 범위의 자식 식별자 범위의 시작을 지정 하여 알림 메시지를 처리 하는 자식 식별자를 지정 합니다.  
  
 클래스 마법사는 **ON\_NOTIFY\_RANGE** 를 처리하지 않습니다. 이 것을 사용하려면 메세지 맵을 직접 편집해야 합니다.  
  
 **ON\_NOTIFY\_RANGE** 에 대한 메시지 맵 엔트리 및 함수 프로토타입은 다음과 같습니다.  
  
```  
  
ON_NOTIFY_RANGE(   
wNotifyCode  
,   
id  
,   
idLast  
,   
memberFxn  
 )  
  
```  
  
 기울임꼴로 표시 된 매개 변수로 대체 됩니다.  
  
 `wNotifyCode`  
 알림 메세지의 코드는 **LVN\_KEYDOWN** 와 같이 처리됩니다.  
  
 `id`  
 식별자의 연속된 범위에서 첫 번째 식별자입니다.  
  
 `idLast`  
 식별자의 연속된 범위에서 마지막 식별자입니다.  
  
 `memberFxn`  
 이 알림이 전송될 때 호출되는 멤버 함수입니다.  
  
 멤버 함수는 다음과 같은 프로토타입을 사용 하여 선언 해야 합니다.  
  
```  
  
afx_msg void memberFxn( UINT id, NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## 설명  
 여기서 기울임꼴 매개 변수는 다음과 같습니다.  
  
 `id`  
 알림을 보낸 컨트롤의 자식 식별자입니다.  
  
 `pNotifyStruct`  
 위에서 설명한 알림 구조체에 대한 포인터입니다.  
  
 *result*  
 반환하기 전에 설정한 결과 코드에 대한 포인터입니다.  
  
##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON\_NOTIFY\_EX, ON\_NOTIFY\_EX\_RANGE  
 메세지를 처리하기 위해 알림 라우팅에서 하나 이상의 개체가 필요한 경우, `ON_NOTIFY`\(또는 **ON\_NOTIFY\_RANGE**\) 보다는 **ON\_NOTIFY\_EX**\(또는 **ON\_NOTIFY\_EX\_RANGE**\) 를 사용하십시오.  **EX** 버전과 일반 버전의 유일한 차이는 함수가 **EX** 버전에 대해 호출한 경우 메세지 처리가 계속 되는 지에 대한 여부를 나타내는 **BOOL** 을 반환한다는 것입니다.  이 함수에서 **FALSE** 를 반환하는 것은 하나 이상의 개체에서 동일한 메세지 처리를 하용합니다.  
  
 클래스 마법사는 **ON\_NOTIFY\_EX** 또는 **ON\_NOTIFY\_EX\_RANGE** 를 처리하지 않습니다. 만약 이 것을 사용하고 싶다면, 메세지 맵을 직접 편집해야 합니다.  
  
 **ON\_NOTIFY\_EX** 및 **ON\_NOTIFY\_EX\_RANGE** 에 대한 메세지 맵 엔트리와 함수 프로토타입은 다음과 같습니다.  매개 변수의 의미는 **EX** 이 아닌 버전과 동일합니다.  
  
```  
  
ON_NOTIFY_EX( nCode, id, memberFxn ) ON_NOTIFY_EX_RANGE( wNotifyCode, id, idLast, memberFxn )  
```  
  
 둘 모두에 대한 프로토타입은 같습니다.  
  
```  
  
afx_msg BOOL memberFxn( UINT id, NMHDR * pNotifyStruct, LRESULT * result );  
```  
  
## 설명  
 두 경우 모두 `id` 는 알림을 보낸 컨트롤의 자식 식별자를 포함 합니다.  
  
 알림 메세지가 완전히 처리 되거나 다른 개체가 명령 라우팅에서 메세지를 처리할 수 있는 기회가 있는 경우 **FALSE** 일 때, 함수는 **TRUE** 를 반환합니다.  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)