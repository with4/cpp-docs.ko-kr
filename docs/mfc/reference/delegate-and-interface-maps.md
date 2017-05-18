---
title: "대리자 및 인터페이스 맵을 매크로 (MFC) | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- delegate map macros
- event map macros
- interface map macros
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
caps.latest.revision: 1
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9b6bd91f5fe02f3747a104be13b448d503af843c
ms.openlocfilehash: 51bf4627c8939a381ceaf14d51d05518b3859718
ms.contentlocale: ko-kr
ms.lasthandoff: 04/22/2017

---

|||  
|-|-|  
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|대리자 맵에 시작합니다.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|인터페이스 맵 정의 시작 합니다.|
|[CommandHandler 대리자](#commandhandler)|명령 소스가 된 콜백 메서드를 등록합니다.  |
|[END_DELEGATE_MAP](#end_delegate_map)|대리자 맵에 종료 됩니다.|
|[END_INTERFACE_MAP](#end_interface_map)|인터페이스 맵을 구현 파일에서을 종료합니다. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|대리자 맵에 항목을 만듭니다.|
|[INTERFACE_PART](#interface_part)|사이 사용 된 `BEGIN_INTERFACE_MAP` 매크로 및 `END_INTERFACE_MAP` 개체에서 지원할 각 인터페이스에 대 한 매크로입니다.|
|[MAKE_DELEGATE](#make_delegate)|관리 되는 컨트롤에 이벤트 처리기를 연결합니다.|


## <a name="begin_delegate_map"></a>BEGIN_DELEGATE_MAP
대리자 맵에 시작합니다.  
   
### <a name="syntax"></a>구문    
```  
BEGIN_DELEGATE_MAP(  CLASS );  
```
### <a name="parameters"></a>매개 변수  
 `CLASS`  
 관리 되는 컨트롤 호스트 되는 클래스입니다.  
   
### <a name="remarks"></a>설명  
 이 매크로의 대리자 맵에 작성 대리자 항목 목록의 시작 부분을 표시 합니다. 이 매크로 사용 하는 방식의 예제를 보려면 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** msclr\event.h  
   
### <a name="see-also"></a>참고 항목  
 [방법: 네이티브 C++ 클래스에서 Windows Forms 이벤트 싱크](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)
 
##  <a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP
구현 파일에서 사용 될 때 인터페이스 맵의 정의 시작 합니다.  
   
### <a name="syntax"></a>구문    
```
BEGIN_INTERFACE_MAP( theClass, baseClass )  
```
### <a name="parameters"></a>매개 변수  
 `theClass`  
 인터페이스 맵을 정의할 클래스  
  
 `baseClass`  
 `theClass`가 파생되는 클래스  
   
### <a name="remarks"></a>설명  
 구현 되는 각 인터페이스에 대해 없는 하나 이상의 `INTERFACE_PART` 매크로 호출이 있습니다. 클래스에서 사용 하는 각 집계에 대해 하나도 **INTERFACE_AGGREGATE** 매크로 호출 합니다.  
  
 인터페이스 맵에 대 한 자세한 내용은 참조 하십시오. [기술 참고 38](../tn038-mfc-ole-iunknown-implementation.md)합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
 
##  <a name="commandhandler"></a>CommandHandler 대리자
명령 소스가 된 콜백 메서드를 등록합니다.  
   
### <a name="syntax"></a>구문    
```  
delegate void CommandHandler(  UINT^ cmdID  );  
```
### <a name="parameters"></a>매개 변수  
 `cmdID`  
 명령 ID입니다.  
   
### <a name="remarks"></a>설명  
 이 대리자 명령 소스를 콜백 메서드를 등록합니다. 명령 원본 개체에 대리자를 추가 하면 콜백 메서드는 지정 된 소스에서 가져온 명령에 대 한 처리기를 됩니다.  
  
 자세한 내용은 참조 [하는 방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)합니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)  
   
### <a name="see-also"></a>참고 항목  
 [방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)
 
##  <a name="commanduihandler"></a>CommandUIHandler
사용자 인터페이스 업데이트 명령 메시지를 콜백 메서드를 등록합니다.  
   
### <a name="syntax"></a>구문    
```  
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);  
```
### <a name="parameters"></a>매개 변수  
 `cmdID`  
 명령 ID입니다.  
  
 `cmdUI`  
 명령 메시지 id입니다.  
   
### <a name="remarks"></a>설명  
 이 대리자 콜백 메서드는 사용자 인터페이스 업데이트 명령 메시지에 등록합니다. `CommandUIHandler`유사한 [CommandHandler](#commandhandler) 제외 하 고이 대리자는 사용자 인터페이스 개체 업데이트 명령과 함께 사용 합니다. 사용자 인터페이스 업데이트 명령 매핑되어야 일대일 메시지 처리기 메서드를 사용 합니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)  
   
### <a name="see-also"></a>참고 항목  
 [방법: 추가 명령 라우팅 windows Forms 컨트롤](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [CommandHandler](#commandhandler)

##  <a name="end_delegate_map"></a>END_DELEGATE_MAP
대리자 맵에 종료 됩니다.  
   
### <a name="syntax"></a>구문    
```  
END_DELEGATE_MAP();  
```  
   
### <a name="remarks"></a>설명  
 이 매크로 대리자 맵에 구성 하는 대리자 항목 목록의 끝을 표시 합니다. 이 매크로 사용 하는 방식의 예제를 보려면 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** msclr\event.h  
   
### <a name="see-also"></a>참고 항목  

 [방법: 네이티브 C++ 클래스에서 Windows Forms 이벤트 싱크](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

 
##  <a name="end_interface_map"></a>END_INTERFACE_MAP
인터페이스 맵을 구현 파일에서을 종료합니다.  
   
### <a name="syntax"></a>구문    
```
END_INTERFACE_MAP( )    
```  
   
### <a name="remarks"></a>설명  
 인터페이스 맵에 대 한 자세한 내용은 참조 하십시오. [기술 참고 38](../tn038-mfc-ole-iunknown-implementation.md)합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [BEGIN_INTERFACE_MAP](#begin_interface_map)
 

##  <a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY
대리자 맵에 항목을 만듭니다.  
   
### <a name="syntax"></a>구문    
```  
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);  
```
### <a name="parameters"></a>매개 변수  
 `MEMBER`  
 컨트롤에 연결할 이벤트 처리기 메서드입니다.  
  
 `ARG0`  
 관리 되는 이벤트 처리기 메서드의 첫 번째 인수 같은 **개체 ^**합니다.  
  
 `ARG1`  
 관리 되는 이벤트 처리기 메서드의 두 번째 인수 같은 **EventArgs ^**합니다.  
   
### <a name="remarks"></a>설명  
 대리자 맵에의 각 항목에서 만든 관리 되는 이벤트 처리기 대리자에 게 해당 [MAKE_DELEGATE](#make_delegate)합니다.  
   
### <a name="example"></a>예제  
 다음 코드 예제는 `EVENT_DELEGATE_ENTRY`를 사용해서 `OnClick` 이벤트 처리기에 대해 대리자 맵에 항목을 만드는 방법을 보여줍니다. `MAKE_DELEGATE`의 코드 예제도 참조하십시오. 자세한 내용은 참조 [하는 방법: 네이티브 c + + 클래스에서 Windows Forms 이벤트 싱크](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)합니다.  
  
 ```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()

```  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** msclr\event.h  
   
### <a name="see-also"></a>참고 항목  
 [MAKE_DELEGATE](#make_delegate)   
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)
 

##  <a name="interface_part"></a>INTERFACE_PART
사이 사용 된 `BEGIN_INTERFACE_MAP` 매크로 및 `END_INTERFACE_MAP` 개체에서 지원할 각 인터페이스에 대 한 매크로입니다.  
   
### <a name="syntax"></a>구문    
```
INTERFACE_PART( theClass, iid, localClass)  
```
### <a name="parameters"></a>매개 변수  
 `theClass`  
 인터페이스 맵을 포함하는 클래스의 이름    
 `iid`  
 포함된 된 클래스에 매핑할 수 있는 IID입니다.    
 *localClass*  
 로컬 클래스의 이름입니다.  
   
### <a name="remarks"></a>설명  
 에 의해 표시 되는 클래스의 멤버에 IID를 매핑할 수 있습니다 `theClass` 및 *localClass*합니다.  
  
 인터페이스 맵에 대 한 자세한 내용은 참조 하십시오. [기술 참고 38](../tn038-mfc-ole-iunknown-implementation.md)합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
   
 
##  <a name="make_delegate"></a>MAKE_DELEGATE
관리 되는 컨트롤에 이벤트 처리기를 연결합니다.  
   
### <a name="syntax"></a>구문    
```  
MAKE_DELEGATE( DELEGATE,  MEMBER) ;  
```
### <a name="parameters"></a>매개 변수  
 `DELEGATE`  
 와 같은 관리 되는 이벤트 처리기의 유형은 위임 [EventHandler](assetId:///T:System.EventHandler?qualifyHint=False&autoUpgrade=True)합니다.  
  
 `MEMBER`  
 컨트롤에 연결 될 이벤트 처리기 메서드의 이름입니다.  
   
### <a name="remarks"></a>설명  
 이 매크로 형식의 관리 되는 이벤트 처리기 대리자를 만듭니다. `DELEGATE` 및 이름의 `MEMBER`합니다. 관리 되는 이벤트 처리기 대리자에는 관리 되는 이벤트를 처리 하는 네이티브 클래스 수 있습니다.  
   
### <a name="example"></a>예제  
 다음 코드 예제에서는 호출 하는 방법을 보여 줍니다. `MAKE_DELEGATE` 연결할는 `OnClick` MFC 컨트롤에 이벤트 처리기 `MyControl`합니다. 이 매크로 MFC 응용 프로그램에서 작동 하는 방법에 대 한 보다 광범위 한 설명을 참조 하십시오. [하는 방법: 네이티브 c + + 클래스에서 Windows Forms 이벤트 싱크](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)합니다.  
  
```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```
   
### <a name="requirements"></a>요구 사항  
 **헤더:** msclr\event.h  
   
### <a name="see-also"></a>참고 항목  
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)
 




