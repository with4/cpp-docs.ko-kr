---
title: 'TN062: Windows 컨트롤에 대 한 리플렉션의 메시지 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.controls.messages
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_VKEYTOITEM_REFLECT macro [MFC]
- ON_WM_DRAWITEM_REFLECT macro [MFC]
- ON_WM_VSCROLL_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT message [MFC]
- ON_CONTROL_REFLECT_EX macro [MFC]
- ON_UPDATE_COMMAND_UI_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT_EX message [MFC]
- ON_WM_HSCROLL_REFLECT macro [MFC]
- message reflection [MFC]
- ON_WM_COMPAREITEM_REFLECT macro [MFC]
- ON_WM_MEASUREITEM_REFLECT macro [MFC]
- ON_NOTIFY message [MFC]
- WM_COMMAND [MFC]
- WM_CTLCOLOR message [MFC]
- TN062 [MFC]
- ON_WM_CHARTOITEM_REFLECT macro [MFC]
- ON_WM_CTLCOLOR_REFLECT macro [MFC]
- ON_WM_DELETEITEM_REFLECT macro [MFC]
- notification messages [MFC]
- ON_WM_PARENTNOTIFY_REFLECT macro [MFC]
- WM_NOTIFY message [MFC]
- ON_CONTROL_REFLECT macro
ms.assetid: 53efb0ba-fcda-4fa0-a3c7-14e0b78fb494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba8e9cac3b7f7997da8c620966234a630b9b9fbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384965"
---
# <a name="tn062-message-reflection-for-windows-controls"></a>TN062: Windows 컨트롤에 대한 메시지 리플렉션
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 기술 노트에서는 메시지 리플렉션, MFC 4.0의 새로운 기능을 설명합니다. 또한 메시지 리플렉션을 사용 하는 간단한 다시 사용할 수 있는 컨트롤을 만드는 지침을 포함 합니다.  
  
 이 기술 노트는 ActiveX 컨트롤 (이전의 OLE 컨트롤)에 적용 될 때 메시지 리플렉션을 설명 하지 않습니다. 문서를 참조 하십시오 [ActiveX 컨트롤: Windows 컨트롤 서브클래싱](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)합니다.  
  
 **메시지 리플렉션 이란**  
  
 Windows 컨트롤 자주 해당 부모 창에 알림 메시지를 전송 합니다. 여러 컨트롤을 컨트롤 색 알림 메시지를 전송 하는 예를 들어, (`WM_CTLCOLOR` 또는 해당 변형 중 하나)를 해당 부모 부모 컨트롤의 배경을 그리는 데 브러시를 제공할 수 있도록 합니다.  
  
 Windows 및 MFC 버전 4.0이 부모 창의 종종 대화 상자는 이러한 메시지를 처리 하는 일을 담당 합니다. 메시지 처리를 위한 코드 부모 창 클래스에 있어야 하 고 해당 메시지를 처리 하는 모든 클래스에 복제 하려면 있음을 의미 합니다. 위의 경우에서 컨트롤 사용자 지정 배경으로 지정 하려는 모든 대화 상자 컨트롤 색 알림 메시지를 처리 해야 합니다. 훨씬 쉽게 하는 자체 배경색을 처리 하려고 하는 컨트롤 클래스를 작성할 수 하는 경우에 코드를 다시 사용 됩니다.  
  
 MFC 4.0에서 이전 메커니즘에도 작동-부모 창 알림 메시지를 처리할 수 있습니다. 그러나 또한 MFC 4.0을 용이 하 게 다시 사용할 수 있도록 "리플렉션 메시지" 이라는 기능을 제공 하 여 이러한 알림 메시지를 자식 컨트롤 창 또는 부모 창에서 나 둘 다에서 처리할 수 있도록 합니다. 컨트롤 배경 색 예제에서 작성할 수 있습니다는 반사를 처리 하 여 자체 배경색을 설정 하는 컨트롤 클래스 `WM_CTLCOLOR` 메시지-부모에 의존 하지 않고도 합니다. (메시지 리플렉션 MFC에서 구현 되는 경우 이후 하지 Windows가 부모 창 클래스 해야 수에서 파생 된 `CWnd` 메시지 리플렉션에 실행 되도록 합니다.)  
  
 이전 버전의 MFC 소유자가 그린 목록 상자에 대 한 메시지와 같은 적은 수의 메시지에 대 한 가상 함수를 제공 하 여 메시지 리플렉션과 비슷한 않았습니다 (`WM_DRAWITEM`등). 새 메시지 리플렉션 메커니즘에는 일반화 되 고 일관 된은입니다.  
  
 메시지 리플렉션 4.0 이전 버전의 MFC 용으로 작성 된 코드와 호환 됩니다.  
  
 특정 메시지에 대 한 처리기를 제공 했지만 또는 부모 창의 클래스에서 메시지의 범위에 대 한이 파일로 재정의 됩니다 하는 경우 사용자 고유의 처리기에서 기본 클래스 처리기 함수를 호출 하지 않으면 제공 동일한 메시지에 대 한 메시지 처리기를 반영 합니다. 예를 들어, 처리 하는 경우 `WM_CTLCOLOR` 대화 상자 클래스를 처리 리플 렉 트 된 메시지 처리기를 재정의 합니다.  
  
 특정에 대 한 처리기에서 부모 창 클래스를 제공 하는 경우 **WM_NOTIFY** 메시지 또는 요소의 범위 **WM_NOTIFY** 메시지를 해당 메시지를 전송 하는 자식 컨트롤에 있는 경우에 호출할 수 처리기 리플 렉 트 된 메시지 처리기를 통해 없는 **ON_NOTIFY_REFLECT()** 합니다. 사용 하는 경우 **ON_NOTIFY_REFLECT_EX()** 메시지 맵에서 메시지 처리기 수 또는 부모 창 메시지를 처리 하기를 사용할 수 없습니다. 처리기에서 반환 하는 경우 **FALSE**, 메시지를 반환 하는 호출 하는 동안 부모도에서 처리 되는 **TRUE** 취급 하는 데 부모를 허용 하지 않습니다. 참고 리플 렉 트 된 메시지는 알림 메시지 보다 먼저 처리 됩니다.  
  
 경우는 **WM_NOTIFY** 메시지가 전송 된, 컨트롤은 첫 번째 예외를 처리를 제공 합니다. 다른 리플 렉 트 된 메시지를 보내는 경우 부모 창에는 첫 번째 예외를 처리 하 고 리플 렉 트 된 메시지를 받을 컨트롤입니다. 이렇게 하려면 처리기 함수 및 컨트롤의 클래스 메시지 맵에 적합 한 항목 필요 합니다.  
  
 리플 렉 트 된 메시지에 대 한 메시지 맵 매크로 일반 알림에 대 한 보다 약간 다른: 있기 **_REFLECT** 일반적인 이름에 추가 됩니다. 예를 들어 처리 하는 **WM_NOTIFY** 메시지 매크로 사용 하면 부모에 `ON_NOTIFY` 부모의 메시지 맵에 있습니다. 자식 컨트롤의 리플 렉 트 된 메시지를 처리 하려면는 **ON_NOTIFY_REFLECT** 자식 컨트롤의 메시지 맵에서 매크로입니다. 경우에 따라 매개 변수도 서로 합니다. 참고 클래스 마법사 수 일반적으로 메시지 맵 항목으로 추가 하 고 올바른 매개 변수가 있는 기초 함수 구현을 제공 합니다.  
  
 참조 [TN061: ON_NOTIFY 및 WM_NOTIFY 메시지](../mfc/tn061-on-notify-and-wm-notify-messages.md) 새에 대 한 내용은 **WM_NOTIFY** 메시지입니다.  
  
 **리플 렉 트 된 메시지에 대 한 처리기 함수 프로토타입 및 메시지 맵 항목**  
  
 리플 렉 트 된 컨트롤 알림 메시지를 처리 하려면 메시지 맵 매크로 및 아래 표에 나열 된 함수 프로토타입을 사용 합니다.  
  
 일반적으로 classwizard 함께 사용 하면에 대 한 이러한 메시지 맵 항목을 추가 하 고 기초 함수 구현을 제공 수입니다. 참조 [반영 메시지에 대 한 메시지 처리기를 정의](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) 리플 렉 트 된 메시지에 대 한 처리기를 정의 하는 방법에 대 한 정보에 대 한 합니다.  
  
 앞에서 메시지 이름이 반영된 매크로 이름으로 변환 하려면 **ON_** 및 추가 **_REFLECT**합니다. 예를 들어 `WM_CTLCOLOR` 됩니다 **ON_WM_CTLCOLOR_REFLECT**합니다. (메시지를 반영 될 수 있습니다를 보려면 반대 변환을 수행할 아래 표에 매크로 항목에.)  
  
 위의 규칙에 세 가지 예외는 다음과 같습니다.  
  
-   에 대 한 매크로 **WM_COMMAND** 알림을 **ON_CONTROL_REFLECT**합니다.  
  
-   에 대 한 매크로 **WM_NOTIFY** 반사는 **ON_NOTIFY_REFLECT**합니다.  
  
-   에 대 한 매크로 `ON_UPDATE_COMMAND_UI` 반사는 **ON_UPDATE_COMMAND_UI_REFLECT**합니다.  
  
 위와 같은 특별 한 경우 각 처리기 멤버 함수 이름을 지정 해야 합니다. 다른 경우에 처리기 함수에 대 한 표준 이름을 사용 해야 합니다.  
  
 매개 변수의 의미 및 함수 반환 값은 함수 이름 또는 함수 이름 앞에서 설명 되어 **에** 앞에 추가 합니다. 예를 들어, **CtlColor** 에 설명 되어 `OnCtlColor`합니다. 몇 가지 리플 렉 트 된 메시지 처리기 해야 매개 변수가 부모 창에서 유사한 처리기 보다 적습니다. 설명서의 정식 매개 변수 이름 사용 하 여 아래 테이블에 있는 이름만 일치 합니다.  
  
|맵 항목|함수 프로토타입|  
|---------------|------------------------|  
|**ON_CONTROL_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **();**|  
|**ON_NOTIFY_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **(NMHDR \***  `pNotifyStruct` **, LRESULT\***  *결과* **);**|  
|**ON_UPDATE_COMMAND_UI_REFLECT (** `memberFxn` **)**|**afx_msg void** `memberFxn` **(CCmdUI\***  `pCmdUI` **);**|  
|**ON_WM_CTLCOLOR_REFLECT)**|**HBRUSH CtlColor afx_msg (CDC\***  `pDC` **, UINT** `nCtlColor` **);**|  
|**ON_WM_DRAWITEM_REFLECT)**|**afx_msg DrawItem void (LPDRAWITEMSTRUCT** `lpDrawItemStruct` **);**|  
|**ON_WM_MEASUREITEM_REFLECT)**|**afx_msg MeasureItem void (LPMEASUREITEMSTRUCT** `lpMeasureItemStruct` **);**|  
|**ON_WM_DELETEITEM_REFLECT)**|**afx_msg를 받지 못하게 DeleteItem (LPDELETEITEMSTRUCT** `lpDeleteItemStruct` **);**|  
|**ON_WM_COMPAREITEM_REFLECT)**|**afx_msg int CompareItem (LPCOMPAREITEMSTRUCT** `lpCompareItemStruct` **);**|  
|**ON_WM_CHARTOITEM_REFLECT)**|**afx_msg int CharToItem (UINT** `nKey` **, UINT** `nIndex` **);**|  
|**ON_WM_VKEYTOITEM_REFLECT)**|**afx_msg int VKeyToItem (UINT** `nKey` **, UINT** `nIndex` **);**|  
|**ON_WM_HSCROLL_REFLECT)**|**afx_msg HScroll void (UINT** `nSBCode` **, UINT** `nPos` **);**|  
|**ON_WM_VSCROLL_REFLECT)**|**afx_msg VScroll void (UINT** `nSBCode` **, UINT** `nPos` **);**|  
|**ON_WM_PARENTNOTIFY_REFLECT)**|**afx_msg ParentNotify void (UINT** `message` **, LPARAM** `lParam` **);**|  
  
 **ON_NOTIFY_REFLECT** 및 **ON_CONTROL_REFLECT** 매크로 변형 된 지정 된 메시지를 처리 하려면 둘 이상의 개체 (예: 컨트롤 및 해당 상위 항목)를 허용 합니다.  
  
|맵 항목|함수 프로토타입|  
|---------------|------------------------|  
|**ON_NOTIFY_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg BOOL** `memberFxn` **(NMHDR \***  `pNotifyStruct` **, LRESULT\***  *결과* **);**|  
|**ON_CONTROL_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg BOOL** `memberFxn` **();**|  
  
## <a name="handling-reflected-messages-an-example-of-a-reusable-control"></a>리플렉션 메시지 처리: 재사용 가능한 컨트롤의 예  
 이 간단한 예제 이라는 재사용 가능한 컨트롤을 만듭니다. `CYellowEdit`합니다. 컨트롤 노란색 배경 기반 검은색 텍스트를 표시 한다는 일반 편집 컨트롤로 동일 하 게 작동 합니다. 것은 쉽게 허용 하는 멤버 함수를 추가할 수는 `CYellowEdit` 컨트롤을 다른 색을 표시 합니다.  
  
#### <a name="to-try-the-example-that-creates-a-reusable-control"></a>재사용 가능한 컨트롤을 만드는 예제를 실행 하려면  
  
1.  기존 응용 프로그램에서 새 대화 상자를 만듭니다. 자세한 내용은 참조는 [대화 상자 편집기](../windows/dialog-editor.md) 항목입니다.  
  
     다시 사용할 수 있는 컨트롤을 개발 하는 응용 프로그램이 있어야 합니다. 사용 하도록 기존 응용 프로그램에 없을 경우 응용 프로그램 마법사를 사용 하 여 대화 상자 기반 응용 프로그램을 만듭니다.  
  
2.  Visual c + +에 로드 된 프로젝트를 사용 하 여 클래스 마법사 라는 새 클래스를 만들고 `CYellowEdit` 기반 `CEdit`합니다.  
  
3.  세 개의 멤버 변수를 추가 하면 `CYellowEdit` 클래스입니다. 처음 두 됩니다 **COLORREF** 텍스트 색과 배경색을 저장 하기 위한 변수입니다. 세 번째는 `CBrush` 배경색을 칠하지에 대 한 브러시를 보유 하는 개체입니다. `CBrush` 개체를 사용 하면, ज ा त 단순히 그 후 참조 하는 브러시를 작성 하 고 브러시를 자동으로 삭제 하는 `CYellowEdit` 컨트롤 소멸 됩니다.  
  
4.  다음과 같이 생성자를 작성 하 여 멤버 변수를 초기화 합니다.  
  
 ```  
    CYellowEdit::CYellowEdit() 
 {  
    m_clrText = RGB(0,
    0,
    0);

    m_clrBkgnd = RGB(255,
    255,
    0);

    m_brBkgnd.CreateSolidBrush(m_clrBkgnd);

 }  
 ```  
  
5.  반영 된에 대 한 처리기 클래스 마법사를 사용 하 여 추가 `WM_CTLCOLOR` 메시지를 사용자 `CYellowEdit` 클래스입니다. Note를 처리할 수 있습니다 메시지의 목록에서 메시지 이름 앞에 등호 기호 있음을 나타내도록 메시지 내용이 반영 됩니다. 에 설명 되어 [반영 메시지에 대 한 메시지 처리기를 정의](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)합니다.  
  
     Classwizard 함께 사용 하면에 대 한 다음 메시지 맵 매크로 및 기본 함수를 추가합니다.  
  
 ```  
    ON_WM_CTLCOLOR_REFLECT() 
 *// Note: other code will be in between....  
 
    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)   
 { *// TODO: Change any attributes of the DC here  
 *// TODO: Return a non-NULL brush if the *//   parent's handler should not be called  
    return NULL;  
 }  
 ```  
  
6.  함수 본문을 다음 코드로 바꿉니다. 코드의 텍스트 색, 텍스트 배경색 및 컨트롤의 나머지 부분에 대 한 배경색을 지정합니다.  
  
 ```  
    pDC->SetTextColor(m_clrText);
*// text  
    pDC->SetBkColor(m_clrBkgnd);
*// text bkgnd  
    return m_brBkgnd;            // ctl bkgnd  
 ```  
  
7.  대화 상자에서 편집 컨트롤 작성 한 다음 편집 컨트롤에 컨트롤 키를 누른 채 두 번 클릭을 멤버 변수에 연결 합니다. 멤버 변수 추가 대화 상자에서 변수 이름을 완료 하 고 "CYellowEdit" 변수 형식에 대 한 범주에 대 한 "제어"를 선택 합니다. 반드시 대화 상자에서 탭 순서를 설정 합니다. 또한,에 대 한 헤더 파일을 포함 해야는 `CYellowEdit` 대화 상자의 헤더 파일에는 컨트롤입니다.  
  
8.  응용 프로그램을 빌드하고 실행합니다. 편집 컨트롤에는 노란색 배경이 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

