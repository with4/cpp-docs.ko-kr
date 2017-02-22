---
title: "COleControlSite Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControlSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControlSite class"
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleControlSite Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 지정 클라이언트 컨트롤 인터페이스를 지원합니다.  
  
## 구문  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleControlSite::COleControlSite](../Topic/COleControlSite::COleControlSite.md)|`COleControlSite` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleControlSite::BindDefaultProperty](../Topic/COleControlSite::BindDefaultProperty.md)|호스팅된 컨트롤의 기본 속성을 데이터 소스에 바인딩합니다.|  
|[COleControlSite::BindProperty](../Topic/COleControlSite::BindProperty.md)|호스팅된 컨트롤의 속성을 데이터 소스에 바인딩합니다.|  
|[COleControlSite::CreateControl](../Topic/COleControlSite::CreateControl.md)|ActiveX 호스트 컨트롤을 만듭니다.|  
|[COleControlSite::DestroyControl](../Topic/COleControlSite::DestroyControl.md)|호스팅된 컨트롤을 소멸 시킵니다.|  
|[COleControlSite::DoVerb](../Topic/COleControlSite::DoVerb.md)|호스팅된 컨트롤의 특정 동사를 실행합니다.|  
|[COleControlSite::EnableDSC](../Topic/COleControlSite::EnableDSC.md)|데이터를 컨트롤 사이트에 대 한 소싱 있습니다.|  
|[COleControlSite::EnableWindow](../Topic/COleControlSite::EnableWindow.md)|컨트롤 사이트를 수 있습니다.|  
|[COleControlSite::FreezeEvents](../Topic/COleControlSite::FreezeEvents.md)|컨트롤 사이트 이벤트를 수락 하는 경우를 지정 합니다.|  
|[COleControlSite::GetDefBtnCode](../Topic/COleControlSite::GetDefBtnCode.md)|호스팅된 컨트롤의 기본 단추 코드를 검색합니다.|  
|[COleControlSite::GetDlgCtrlID](../Topic/COleControlSite::GetDlgCtrlID.md)|컨트롤의 식별자를 검색합니다.|  
|[COleControlSite::GetEventIID](../Topic/COleControlSite::GetEventIID.md)|호스팅된 컨트롤의 이벤트 인터페이스의 ID를 검색합니다.|  
|[COleControlSite::GetExStyle](../Topic/COleControlSite::GetExStyle.md)|확장된 스타일의 컨트롤 사이트를 검색합니다.|  
|[COleControlSite::GetProperty](../Topic/COleControlSite::GetProperty.md)|호스팅된 컨트롤의 특정 속성을 검색합니다.|  
|[COleControlSite::GetStyle](../Topic/COleControlSite::GetStyle.md)|제어 사이트의 스타일을 검색합니다.|  
|[COleControlSite::GetWindowText](../Topic/COleControlSite::GetWindowText.md)|호스팅된 컨트롤의 텍스트를 검색합니다.|  
|[COleControlSite::InvokeHelper](../Topic/COleControlSite::InvokeHelper.md)|호스팅된 컨트롤의 특정 메서드를 호출 합니다.|  
|[COleControlSite::InvokeHelperV](../Topic/COleControlSite::InvokeHelperV.md)|가변 인수 목록에 호스팅되는 컨트롤의 특정 메서드를 호출 합니다.|  
|[COleControlSite::IsDefaultButton](../Topic/COleControlSite::IsDefaultButton.md)|컨트롤 창에서 기본 단추 인지 여부를 확인 합니다.|  
|[COleControlSite::IsWindowEnabled](../Topic/COleControlSite::IsWindowEnabled.md)|제어 사이트의 표시 상태를 확인합니다.|  
|[COleControlSite::ModifyStyle](../Topic/COleControlSite::ModifyStyle.md)|현재 확장 컨트롤 사이트의 스타일을 수정 합니다.|  
|[COleControlSite::ModifyStyleEx](../Topic/COleControlSite::ModifyStyleEx.md)|제어 사이트의 현재 스타일을 수정합니다.|  
|[COleControlSite::MoveWindow](../Topic/COleControlSite::MoveWindow.md)|컨트롤 사이트 위치가 변경 됩니다.|  
|[COleControlSite::QuickActivate](../Topic/COleControlSite::QuickActivate.md)|빠른 호스팅된 컨트롤을 활성화합니다.|  
|[COleControlSite::SafeSetProperty](../Topic/COleControlSite::SafeSetProperty.md)|두번째 예외를 throw 하지 않고 컨트롤의 메서드나 속성을 설정 합니다.|  
|[COleControlSite::SetDefaultButton](../Topic/COleControlSite::SetDefaultButton.md)|창에는 기본 단추를 설정합니다.|  
|[COleControlSite::SetDlgCtrlID](../Topic/COleControlSite::SetDlgCtrlID.md)|컨트롤의 식별자를 검색합니다.|  
|[COleControlSite::SetFocus](../Topic/COleControlSite::SetFocus.md)|컨트롤 사이트에 포커스를 설정합니다.|  
|[COleControlSite::SetProperty](../Topic/COleControlSite::SetProperty.md)|호스팅된 컨트롤의 특정 속성을 설정합니다.|  
|[COleControlSite::SetPropertyV](../Topic/COleControlSite::SetPropertyV.md)|가변 인수 목록에 호스팅되는 컨트롤의 특정 속성을 설정합니다.|  
|[COleControlSite::SetWindowPos](../Topic/COleControlSite::SetWindowPos.md)|제어 사이트의 위치를 설정합니다.|  
|[COleControlSite::SetWindowText](../Topic/COleControlSite::SetWindowText.md)|호스팅된 컨트롤의 텍스트를 설정합니다.|  
|[COleControlSite::ShowWindow](../Topic/COleControlSite::ShowWindow.md)|표시 하거나 제어 사이트를 숨깁니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleControlSite::GetControlInfo](../Topic/COleControlSite::GetControlInfo.md)|호스팅된 컨트롤에 대해 니모닉 및 키보드 정보를 검색합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleControlSite::m\_bIsWindowless](../Topic/COleControlSite::m_bIsWindowless.md)|호스팅된 컨트롤의 창 없는 컨트롤 인지 확인 합니다.|  
|[COleControlSite::m\_ctlInfo](../Topic/COleControlSite::m_ctlInfo.md)|키보드 제어에 대 한 처리에 대 한 정보가 들어 있습니다.|  
|[COleControlSite::m\_dwEventSink](../Topic/COleControlSite::m_dwEventSink.md)|쿠키의 컨트롤의 연결 지점입니다.|  
|[COleControlSite::m\_dwMiscStatus](../Topic/COleControlSite::m_dwMiscStatus.md)|호스팅된 컨트롤에 대 한 기타 상태입니다.|  
|[COleControlSite::m\_dwPropNotifySink](../Topic/COleControlSite::m_dwPropNotifySink.md)|`IPropertyNotifySink` 컨트롤의 쿠키입니다.|  
|[COleControlSite::m\_dwStyle](../Topic/COleControlSite::m_dwStyle.md)|호스팅된 컨트롤의 스타일입니다.|  
|[COleControlSite::m\_hWnd](../Topic/COleControlSite::m_hWnd.md)|핸들 컨트롤 사이트입니다.|  
|[COleControlSite::m\_iidEvents](../Topic/COleControlSite::m_iidEvents.md)|호스팅된 컨트롤의 이벤트 인터페이스의 ID입니다.|  
|[COleControlSite::m\_nID](../Topic/COleControlSite::m_nID.md)|호스팅된 컨트롤의 ID입니다.|  
|[COleControlSite::m\_pActiveObject](../Topic/COleControlSite::m_pActiveObject.md)|에 대 한 포인터는 `IOleInPlaceActiveObject` 호스팅되는 컨트롤의 개체입니다.|  
|[COleControlSite::m\_pCtrlCont](../Topic/COleControlSite::m_pCtrlCont.md)|호스팅된 컨트롤의 컨테이너입니다.|  
|[COleControlSite::m\_pInPlaceObject](../Topic/COleControlSite::m_pInPlaceObject.md)|에 대 한 포인터는 `IOleInPlaceObject` 호스팅되는 컨트롤의 개체입니다.|  
|[COleControlSite::m\_pObject](../Topic/COleControlSite::m_pObject.md)|에 대 한 포인터는 `IOleObjectInterface` 컨트롤의 인터페이스.|  
|[COleControlSite::m\_pWindowlessObject](../Topic/COleControlSite::m_pWindowlessObject.md)|에 대 한 포인터는 `IOleInPlaceObjectWindowless` 컨트롤의 인터페이스.|  
|[COleControlSite::m\_pWndCtrl](../Topic/COleControlSite::m_pWndCtrl.md)|호스팅된 컨트롤의 창 개체에 대 한 포인터입니다.|  
|[COleControlSite::m\_rect](../Topic/COleControlSite::m_rect.md)|제어 사이트의 크기입니다.|  
  
## 설명  
 이 지원 기준이 포함된 ActiveX 컨트롤의 위치와 범위를 해당 표시 사이트, 해당 모니커, 해당 사용자 인터페이스, 앰비언트 속성 및 해당 컨테이너에서 제공 하는 다른 리소스에 대 한 정보 획득 하는 기본 방법입니다.  `COleControlSite`완전히 구현 된  [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502),  [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586),  [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706),  [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638),  **IBoundObjectSite**,  **INotifyDBEvents**,  [IRowSetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) 인터페이스.  또한 IDispatch 인터페이스 \(앰비언트 속성 및 이벤트 싱크 지원\) 구현 됩니다.  
  
 사이트는 ActiveX 컨트롤 사용을 만들려면 `COleControlSite`, 파생 클래스에서 `COleControlSite`.  사용자 `CWnd`\-컨테이너 \(예를 들어, 대화 상자\)에 대 한 파생된 클래스에서 재정의 된  **CWnd::CreateControlSite** 함수.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlSite`  
  
## 요구 사항  
 **헤더:** afxocc.h  
  
## 참고 항목  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleControlContainer Class](../../mfc/reference/colecontrolcontainer-class.md)