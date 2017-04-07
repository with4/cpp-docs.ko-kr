---
title: "메시지 맵 매크로 (MFC) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [C++], declaration
- demarcating Windows messages
- message maps [C++], macros
- message maps [C++], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: 0c5856dce919ca8ea2d396fbf2523dc45409b519
ms.lasthandoff: 03/06/2017

---
# <a name="message-map-macros-mfc"></a>메시지 맵 매크로(MFC)
MFC는 메시지 맵을 지원 하기 위해 다음과 같은 매크로 제공 합니다.  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>메시지 맵 선언 및 구분 매크로  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](#declare_message_map)|메시지 맵 (클래스 선언에 사용 해야 합니다) 함수에 메시지를 매핑하기 위해 클래스에서 사용될지를 선언 합니다.|  
|[BEGIN_MESSAGE_MAP](#begin_message_map)|메시지 맵 (클래스 구현에 사용 해야 합니다)의 정의 시작 합니다.|  
|[END_MESSAGE_MAP](#end_message_map)|메시지 맵 (클래스 구현에 사용 해야 합니다)의 정의 끝냅니다.|  
  
### <a name="message-mapping-macros"></a>메시지 매핑 매크로  
  
|||  
|-|-|  
|[ON_COMMAND](#on_command)|함수는 지정 된 명령 메시지를 처리 하는 것을 나타냅니다.|  
|[ON_CONTROL](#on_control)|함수는 지정 된 컨트롤 알림 메시지를 처리 하는 것을 나타냅니다.|  
|[ON_MESSAGE](#on_message)|함수는 사용자 정의 메시지를 처리할지를 나타냅니다.|  
|[ON_OLECMD](#on_olecmd)|DocObject 또는 해당 컨테이너에서 메뉴 명령을 처리할 함수를 나타냅니다.|  
|[ON_REGISTERED_MESSAGE](#on_registered_message)|함수에서 등록 된 사용자 정의 메시지를 처리할지를 나타냅니다.|  
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|어떤 함수가 있는 경우 등록 된 사용자 정의 메시지를 처리할지 나타냅니다는 `CWinThread` 클래스입니다.|  
|[ON_THREAD_MESSAGE](#on_thread_message)|함수를 사용자 정의 메시지를 처리할 경우 나타냅니다는 `CWinThread` 클래스입니다.|  
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|함수는 지정 된 사용자 인터페이스 업데이트 명령 메시지를 처리할지를 나타냅니다.|  
  
### <a name="message-map-range-macros"></a>메시지 맵 범위 매크로  
  
|||  
|-|-|  
|[ON_COMMAND_RANGE](#on_command_range)|함수 매크로에 처음 두 매개 변수에 지정 된 명령 Id의 범위를 처리할지를 나타냅니다.|  
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|업데이트 처리기를 명령 id의 처음 두 pa에 지정 된 범위를 처리할 나타냅니다] rameters 매크로에 있습니다.|  
|[ON_CONTROL_RANGE](#on_control_range)|함수에서 컨트롤 매크로에 두 번째 및 세 번째 매개 변수에 지정 된 Id의 범위에서 알림을 처리할지를 나타냅니다. 첫 번째 매개 변수는 컨트롤 알림 메시지를와 같은 **BN_CLICKED**합니다.|  
  
 메시지 맵, 메시지 맵 선언 및 구분 매크로 및 메시지 매핑 매크로에 대 한 자세한 내용은 참조 하십시오. [메시지 맵](../../mfc/reference/message-maps-mfc.md) 및 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md)합니다. 메시지 맵 범위에 대 한 자세한 내용은 참조 [메시지 맵 범위에 대 한 처리기](../../mfc/handlers-for-message-map-ranges.md)합니다.  

## <a name="declare_message_map"></a>DECLARE_MESSAGE_MAP
 메시지 맵 클래스를 정의 하는 선언 합니다. 각 `CCmdTarget`-프로그램의 파생된 클래스는 메시지를 처리 한 메시지 맵을 제공 해야 합니다.  
  
### <a name="syntax"></a>구문  
  
```    
DECLARE_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>주의  
 사용 하는 `DECLARE_MESSAGE_MAP` 클래스 선언 후에는 매크로입니다. 그런 다음 클래스 멤버 함수를 정의 하는.cpp 파일에서 사용 하는 `BEGIN_MESSAGE_MAP` 매크로, 메시지-처리기 함수의 각각에 대해 매크로 항목 및 `END_MESSAGE_MAP` 매크로입니다.  
  
> [!NOTE]
>  멤버 다음의 모든 멤버를 선언 하는 경우 `DECLARE_MESSAGE_MAP`, 새 액세스 유형을 지정 해야 합니다 (**공용**, `private`, 또는 `protected`) 해당 합니다.  
  
 메시지에 대 한 자세한 내용은 맵 및 `DECLARE_MESSAGE_MAP` 매크로 참조 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md)합니다.  
  
### <a name="example"></a>예제  
```cpp  
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
``` 
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  

## <a name="begin_message_map"></a>BEGIN_MESSAGE_MAP
메시지 맵 정의 시작합니다.  
  
### <a name="syntax"></a>구문  
  
```  
BEGIN_MESSAGE_MAP( theClass, baseClass )  
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 있는 메시지가 매핑할 클래스의 이름을 지정 합니다.  
  
 `baseClass`  
 `theClass`의 기본 클래스 이름을 지정합니다.  
  
### <a name="remarks"></a>주의  
 클래스 멤버 함수를 정의 하는 구현 (.cpp) 파일에서 메시지 맵을 시작한는 `BEGIN_MESSAGE_MAP` 매크로, 그런 다음 메시지-처리기 함수의 각각에 대해 매크로 항목을 추가 하 고 사용 하 여 메시지 맵을 완료는 `END_MESSAGE_MAP` 매크로입니다.  
  
 메시지 맵에 대 한 자세한 내용은 참조 [메시지 맵](message-maps-mfc.md)  
  
### <a name="example"></a>예제  
```cpp  
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h 

## <a name="end_message_map"></a>END_MESSAGE_MAP
메시지 맵 정의 종료합니다.  
  
### <a name="syntax"></a>구문  
  
```   
END_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>주의  
 메시지에 대 한 자세한 내용은 맵 및 `END_MESSAGE_MAP` 매크로 참조 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  

## <a name="on_command"></a>ON_COMMAND
이 매크로 멤버 함수에 명령 메시지를 매핑합니다.  
  
### <a name="syntax"></a>구문  
  
```  
ON_COMMAND( id, memberFxn )  
```  
  
### <a name="parameters"></a>매개 변수  
 `id`  
 명령 ID입니다.  
  
 `memberFxn`  
 명령이 매핑되는 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 함수를 메뉴 항목이 나 도구 모음 단추를 같은 명령 사용자 인터페이스 개체에서 명령 메시지를 처리할 것을 나타냅니다.  
  
 명령 대상 개체는 Windows를 받았을 때 **WM_COMMAND** 지정 된 id는 메시지 `ON_COMMAND` 멤버 함수를 호출 `memberFxn` 메시지를 처리 합니다.  
  
 사용 하 여 `ON_COMMAND` 명령 중 하나는 멤버 함수에 매핑됩니다. 사용 하 여 [ON_COMMAND_RANGE](#on_command_range) 한 멤버 함수에 명령 id의 범위를 매핑할 수 있습니다. 하나의 메시지-맵 항목에는 지정한 명령 id를 간주할 수 있습니다. 즉, 명령 둘 이상의 처리기에 매핑할 수 없습니다. 자세한 내용 및 예제에 대 한 참조 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md)합니다.  
  
### <a name="example"></a>예제  
```cpp  
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
``` 
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxmsg_.h  
  
## <a name="on_control"></a>ON_CONTROL
함수를 사용자 지정 컨트롤 알림 메시지를 처리할 것을 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```  
ON_CONTROL( wNotifyCode, id, memberFxn )  
```  
  
### <a name="parameters"></a>매개 변수  
 `wNotifyCode`  
 컨트롤의 알림 코드입니다.  
  
 `id`  
 명령 ID입니다.  
  
 `memberFxn`  
 명령이 매핑되는 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 컨트롤 알림 메시지는 해당 부모 창에는 컨트롤에서 전송입니다.  
  
 개 안 `ON_CONTROL` 메시지 처리기 함수에 매핑해야 하는 모든 컨트롤 알림 메시지에 대 한 메시지 맵 매크로 문입니다.  
  
 자세한 내용 및 예제에 대 한 참조 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxmsg_.h  
  

## <a name="on_message"></a>ON_MESSAGE  
함수는 사용자 정의 메시지를 처리할지를 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```  
ON_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>매개 변수  
 `message`  
 메시지 ID입니다.  
  
 `memberFxn`  
 메시지 매핑되는 메시지-처리기 함수의 이름입니다.  
  
 함수 형식의 해야 `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`합니다.  
  
### <a name="remarks"></a>설명  
 사용자 정의 메시지는 표준 Windows가 아닌 모든 메시지 `WM_MESSAGE` 메시지입니다. 메시지 ID를 선택할 때의 범위 내에서 값을 사용 해야 `WM_USER` (0x0400) 0x7FFF를 또는 `WM_APP` (0x8000) 0xBFFF에 있습니다. 메시지 Id에 대 한 자세한 내용은 참조 [WM_APP](http://msdn.microsoft.com/library/windows/desktop/ms644930)합니다.  
  
 개 안 `ON_MESSAGE` 메시지 처리기 함수에 매핑해야 하는 모든 사용자 정의 메시지에 대 한 메시지 맵 매크로 문입니다.  
  
> [!NOTE]
>  사용자 정의 메시지 외에도 `ON_MESSAGE` 덜 일반적인 Windows 메시지를 처리 합니다. 자세한 내용은 기술 자료 문서를 참조 하십시오. [99848: 정보: 맵 덜 일반적인 메시지를 사용 하 여 ON_MESSAGE() 매크로](http://go.microsoft.com/fwlink/?linkId=192022)합니다.  
  
 자세한 내용 및 예제에 대 한 참조 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md) 및 [사용자 정의 처리기](user-defined-handlers.md)  
  
### <a name="example"></a>예제  
```cpp  
#define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd2, CWnd)
   ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()

// inside the class declaration
 afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

 LRESULT CMyWnd2::OnMyMessage(WPARAM wParam, LPARAM lParam)
{
   UNREFERENCED_PARAMETER(wParam);
   UNREFERENCED_PARAMETER(lParam);

   // Handle message here. 

   return 0;
}
```   
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxmsg_.h  

## <a name="on_olecmd"></a>ON_OLECMD    
명령 디스패치 인터페이스를 통해 명령을 라우팅하고 `IOleCommandTarget`합니다.  
  
### <a name="syntax"></a>구문  
  
```  
ON_OLECMD( pguid, olecmdid, id )  
```  
  
### <a name="parameters"></a>매개 변수  
 `pguid`  
 이 명령은 속해 있는 명령 그룹의 식별자입니다. 사용 하 여 **NULL** 표준 그룹에 대 한 합니다.  
  
 *olecmdid*  
 OLE 명령 식별자입니다.  
  
 `id`  
 메뉴 ID, 도구 모음 ID, 단추 ID 또는 리소스 또는 명령을 실행 하는 개체의 다른 ID를 선택 합니다.  
  
### <a name="remarks"></a>설명  
 `IOleCommandTarget`컨테이너에서 동일한 명령을 보낼 수 있으며, DocObject의 사용자 인터페이스에서 발생 하는 명령을 수신 하도록 컨테이너가 허용 (새로 만들기, 열기, 저장 및 인쇄 파일 메뉴와 같은 복사 및 붙여넣기, 실행 취소, 등 편집 메뉴에서) DocObject에 있습니다.  
  
 `IOleCommandTarget`OLE 자동화의 보다 간단한 `IDispatch`합니다. `IOleCommandTarget`표준 명령 집합을 전적으로 의존 거의 하는 인수를 한 형식 정보가 없는 과정이 진행 중 (형식 안전성도 명령 인수에 대 한 감소). 명령 인수를 갖는 디스패치 필요가 없는 경우 사용 하 여 [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)합니다.  
  
 `IOleCommandTarget` 표준 메뉴 명령을 다음 매크로의 MFC에서 구현 되었습니다.  
  
 **ON_OLECMD_CLEARSELECTION)**  
  
 Clear 편집 명령을 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`  
  
 **ON_OLECMD_COPY)**  
  
 복사본 편집 명령을 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`  
  
 **ON_OLECMD_CUT)**  
  
 잘라내기 편집 명령을 전달합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`  
  
 **ON_OLECMD_NEW)**  
  
 새 파일 명령을 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`  
  
 **ON_OLECMD_OPEN)**  
  
 파일 열기 명령을 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`  
  
 **ON_OLECMD_PAGESETUP)**  
  
 파일 페이지 설정 메뉴를 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`  
  
 **ON_OLECMD_PASTE)**  
  
 편집 붙여넣기 명령을 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`  
  
 **ON_OLECMD_PASTESPECIAL)**  
  
 편집 하 여 붙여넣기 명령을 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`  
  
 **ON_OLECMD_PRINT)**  
  
 파일 인쇄 명령을 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`  
  
 **ON_OLECMD_PRINTPREVIEW)**  
  
 파일 인쇄 미리 보기 명령을 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`  
  
 **ON_OLECMD_REDO)**  
  
 다시 실행 편집 명령을 전달합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`  
  
 **ON_OLECMD_SAVE)**  
  
 파일 저장 명령을 전달합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`  
  
 **ON_OLECMD_SAVE_AS)**  
  
 다른 이름으로 저장 명령을 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`  
  
 **ON_OLECMD_SAVE_COPY_AS)**  
  
 파일 복사본으로 저장 명령을 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`  
  
 **ON_OLECMD_SELECTALL)**  
  
 모두 선택 편집 명령을 디스패치합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`  
  
 **ON_OLECMD_UNDO)**  
  
 실행 취소 편집 명령을 전달합니다. 로 구현 합니다.  
  
 `ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxdocob.h  
  
### <a name="see-also"></a>참고 항목  
 [COleCmdUI 클래스](colecmdui-class.md)   
 [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)

## <a name="on_registered_message"></a>ON_REGISTERED_MESSAGE
Windows **RegisterWindowMessage** 함수는 시스템 전체에서 고유 하 게 보장 되는 새 창 메시지를 정의 하는 데 사용 됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>매개 변수  
 `nMessageVariable`  
 등록 된 창 메시지 ID 변수입니다.  
  
 `memberFxn`  
 메시지 매핑되는 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 함수를 등록 된 메시지를 처리할 것을 나타냅니다.  
  
 자세한 내용 및 예제에 대 한 참조 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md)합니다.  
  
### <a name="example"></a>예제  
```cpp  
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));


BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxmsg_.h  
  
### <a name="see-also"></a>참고 항목  
 [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947)   
 [사용자 정의 처리기](user-defined-handlers.md)

## <a name="on_registered_thread_message"></a>ON_REGISTERED_THREAD_MESSAGE    
함수를 Windows RegisterWindowMessage 함수에 의해 등록 된 메시지를 처리할 것을 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```  
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>매개 변수  
 `nMessageVariable`  
 등록 된 창 메시지 ID 변수입니다.  
  
 `memberFxn`  
 메시지 매핑되는 CWinThread-메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 RegisterWindowMessage는 시스템 전체에서 고유 하 게 보장 되는 새 창 메시지를 정의 하는 데 사용 됩니다. CWinThread 클래스 있으면 ON_REGISTERED_THREAD_MESSAGE ON_REGISTERED_MESSAGE 대신 사용 되어야 합니다. 
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxmsg_.h  

## <a name="on_thread_message"></a>ON_THREAD_MESSAGE    
함수는 사용자 정의 메시지를 처리할지를 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```  
ON_THREAD_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>매개 변수  
 `message`  
 메시지 ID입니다.  
  
 `memberFxn`  
 이름을 `CWinThread`-메시지-처리기 함수의 메시지 매핑되는 합니다.  
  
### <a name="remarks"></a>주의  
 `ON_THREAD_MESSAGE`대신 사용 해야 `ON_MESSAGE` 있는 경우는 `CWinThread` 클래스입니다. 사용자 정의 메시지는 표준 Windows가 아닌 모든 메시지 **WM_MESSAGE** 메시지입니다. 개 안 `ON_THREAD_MESSAGE` 메시지 처리기 함수에 매핑해야 하는 모든 사용자 정의 메시지에 대 한 메시지 맵 매크로 문입니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  

## <a name="on_update_command_ui"></a>ON_UPDATE_COMMAND_UI    
이 매크로 함수를 사용자 인터페이스 업데이트 명령 메시지를 처리할 것을 나타냅니다.  
  
### <a name="syntax"></a>구문  
  
```  
ON_UPDATE_COMMAND_UI( id, memberFxn )  
```  
  
### <a name="parameters"></a>매개 변수  
 `id`  
 메시지 ID입니다.  
  
 `memberFxn`  
 메시지 매핑되는 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>설명  
 개 안 `ON_UPDATE_COMMAND_UI` 메시지 처리기 함수에 매핑해야 하는 모든 사용자 인터페이스 업데이트 명령에 대 한 메시지 맵 매크로 문입니다.  
  
 자세한 내용 및 예제에 대 한 참조 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
### <a name="see-also"></a>참고 항목  
 [CCmdUI 클래스](ccmdui-class.md)

## <a name="on_command_range"></a>ON_COMMAND_RANGE  
이 매크로 사용 하 여 명령 Id의 연속 된 범위를 단일 메시지 처리기 함수에 매핑됩니다.  
  
### <a name="syntax"></a>구문
  
```  
ON_COMMAND_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>매개 변수  
 `id1`  
 명령 Id의 연속 된 범위의 시작 부분에서 명령 ID입니다.  
  
 `id2`  
 명령 Id의 연속 된 범위 끝에 명령 ID입니다.  
  
 `memberFxn`  
 명령이 매핑되는 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>설명  
 로 시작 하는 Id 범위 `id1` 하 고 끝나는지 `id2`합니다.  
  
 사용 하 여 `ON_COMMAND_RANGE` 한 멤버 함수에 명령 Id의 범위를 매핑할 수 있습니다. 사용 하 여 [ON_COMMAND](#on_command) 명령 중 하나는 멤버 함수에 매핑됩니다. 하나의 메시지-맵 항목에는 지정한 명령 ID를 일치 시킬 수 있습니다. 즉, 명령 둘 이상의 처리기에 매핑할 수 없습니다. 매핑 메시지 범위에 대 한 자세한 내용은 참조 하십시오. [메시지 맵 범위에 대 한 처리기](../../mfc/handlers-for-message-map-ranges.md)합니다.  
  
 지원은 없습니다 자동 메시지 맵 범위에 대 한 하므로 사용자가 직접 매크로 배치 해야 합니다.  
  
### <a name="example"></a>예제  
```cpp  
// The code fragment below shows how to use ON_COMMAND_RANGE macro 
// to map a contiguous range of command IDs to a single message  
// handler function (i.e. OnRangeCmds() in the sample below). In  
// addition, it also shows how to use CheckMenuRadioItem() to check a  
// selected menu item and makes it a radio item.

BEGIN_MESSAGE_MAP(CChildFrame, CMDIChildWnd)
   ON_COMMAND_RANGE(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, &CChildFrame::OnRangeCmds)
END_MESSAGE_MAP()

void CChildFrame::OnRangeCmds(UINT nID)
{
   CMenu* mmenu = AfxGetMainWnd()->GetMenu();
   CMenu* submenu = mmenu->GetSubMenu(5);
   submenu->CheckMenuRadioItem(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, 
      nID, MF_BYCOMMAND);
}
```
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxmsg_.h  

## <a name="on_update_command_ui_range"></a>ON_UPDATE_COMMAND_UI_RANGE    
명령 Id의 연속 된 범위를 단일 업데이트 메시지 처리기 함수에 매핑됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>매개 변수  
 `id1`  
 명령 Id의 연속 된 범위의 시작 부분에서 명령 ID입니다.  
  
 `id2`  
 명령 Id의 연속 된 범위 끝에 명령 ID입니다.  
  
 `memberFxn`  
 명령이 매핑되는 업데이트 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>주의  
 업데이트 메시지 처리기 명령과 연결 된 도구 모음 단추 및 메뉴 항목의 상태를 업데이트 합니다. 로 시작 하는 Id 범위 `id1` 하 고 끝나는지 `id2`합니다.  
  
 지원은 없습니다 자동 메시지 맵 범위에 대 한 하므로 사용자가 직접 매크로 배치 해야 합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxmsg_.h  

## <a name="on_control_range"></a>ON_CONTROL_RANGE     
이 매크로 사용 하 여 매핑할 컨트롤 Id의 연속 된 범위 지정된 된 Windows 알림 메시지에 대 한 단일 메시지 처리기 함수 같은 **BN_CLICKED**합니다.  
  
### <a name="syntax"></a>구문  
  
```  
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>매개 변수  
 `wNotifyCode`  
 처리기가 응답 하지 알림 코드입니다.  
  
 `id1`  
 컨트롤 Id의 연속 된 범위의 시작 부분에서 명령 ID입니다.  
  
 `id2`  
 컨트롤 Id의 연속 된 범위 끝에 명령 ID입니다.  
  
 `memberFxn`  
 컨트롤 매핑되는 메시지-처리기 함수의 이름입니다.  
  
### <a name="remarks"></a>설명  
 로 시작 하는 Id 범위 `id1` 하 고 끝나는지 `id2`합니다. 매핑된 컨트롤 중 하나에서 가져온 지정 된 알림에 대 한 처리기가 호출 됩니다.  
  
 지원은 없습니다 자동 메시지 맵 범위에 대 한 하므로 사용자가 직접 매크로 배치 해야 합니다.  
  
 컨트롤 Id의 범위에 대 한 처리기 함수를 구현 하는 방법에 대 한 자세한 내용은 참조 [메시지 맵 범위에 대 한 처리기](../../mfc/handlers-for-message-map-ranges.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxmsg_.h  
  



