---
title: "CDHtmlDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDHtmlDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDHtmlDialog class"
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDHtmlDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

HTML 사용 대화 상자를 만드는 데 사용 되는 사용자 인터페이스를 구현 하는 대화 상자 리소스 대신 합니다.  
  
## 구문  
  
```  
class CDHtmlDialog : public CDialog, public CDHtmlEventSink  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDHtmlDialog::CDHtmlDialog](../Topic/CDHtmlDialog::CDHtmlDialog.md)|CDHtmlDialog 개체를 만듭니다.|  
|[CDHtmlDialog::~CDHtmlDialog](../Topic/CDHtmlDialog::~CDHtmlDialog.md)|CDHtmlDialog 개체를 소멸 시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDHtmlDialog::CanAccessExternal](../Topic/CDHtmlDialog::CanAccessExternal.md)|재정의할 수 있는 외부 디스패치 컨트롤 사이트 스크립팅 개체에 로드 된 페이지에서 액세스할 수 있는지 여부를 확인 하려면 액세스 확인으로 라고 합니다.  디스패치 스크립트 사용에 안전 하지 않은 개체에 대해 스크립트 사용에 안전 또는 현재 시간대 허용 되어 있는지 확인 합니다.|  
|[CDHtmlDialog::CreateControlSite](../Topic/CDHtmlDialog::CreateControlSite.md)|재정의 가능 대화 상자에 WebBrowser 컨트롤을 호스팅할 사이트 컨트롤 인스턴스를 만드는 데 사용.|  
|[CDHtmlDialog::DDX\_DHtml\_AxControl](../Topic/CDHtmlDialog::DDX_DHtml_AxControl.md)|속성 값은 HTML 페이지에 ActiveX 컨트롤의 멤버 변수 간에 데이터를 교환합니다.|  
|[CDHtmlDialog::DDX\_DHtml\_CheckBox](../Topic/CDHtmlDialog::DDX_DHtml_CheckBox.md)|HTML 페이지의 확인란 및 멤버 변수 간에 데이터를 교환합니다.|  
|[CDHtmlDialog::DDX\_DHtml\_ElementText](../Topic/CDHtmlDialog::DDX_DHtml_ElementText.md)|HTML 페이지에서 모든 HTML 요소 속성 및 멤버 변수 간에 데이터를 교환합니다.|  
|[CDHtmlDialog::DDX\_DHtml\_Radio](../Topic/CDHtmlDialog::DDX_DHtml_Radio.md)|HTML 페이지에서 라디오 단추와 멤버 변수 간에 데이터를 교환합니다.|  
|[CDHtmlDialog::DDX\_DHtml\_SelectIndex](../Topic/CDHtmlDialog::DDX_DHtml_SelectIndex.md)|HTML 페이지에 목록 상자의 인덱스를 설정 하거나 가져옵니다.|  
|[CDHtmlDialog::DDX\_DHtml\_SelectString](../Topic/CDHtmlDialog::DDX_DHtml_SelectString.md)|HTML 페이지에서 \(현재 인덱스에 따라\) 목록 상자 항목의 표시 텍스트를 가져오거나 설정 합니다.|  
|[CDHtmlDialog::DDX\_DHtml\_SelectValue](../Topic/CDHtmlDialog::DDX_DHtml_SelectValue.md)|HTML 페이지에서 \(현재 인덱스에 따라\) 목록 상자 항목의 값을 가져오거나 설정 합니다.|  
|[CDHtmlDialog::DestroyModeless](../Topic/CDHtmlDialog::DestroyModeless.md)|모덜리스 대화 상자를 소멸 시킵니다.|  
|[CDHtmlDialog::EnableModeless](../Topic/CDHtmlDialog::EnableModeless.md)|모덜리스 대화 상자를 활성화 합니다.|  
|[CDHtmlDialog::FilterDataObject](../Topic/CDHtmlDialog::FilterDataObject.md)|대화 상자를 만든 브라우저에서 호스팅된 클립보드 데이터 개체를 필터링 할 수 있습니다.|  
|[CDHtmlDialog::GetControlDispatch](../Topic/CDHtmlDialog::GetControlDispatch.md)|검색은 `IDispatch` 인터페이스는 ActiveX 컨트롤에 HTML 문서에 포함 합니다.|  
|[CDHtmlDialog::GetControlProperty](../Topic/CDHtmlDialog::GetControlProperty.md)|지정 된 ActiveX 컨트롤의 요청 된 속성을 검색합니다.|  
|[CDHtmlDialog::GetCurrentUrl](../Topic/CDHtmlDialog::GetCurrentUrl.md)|검색 통일 된 리소스 로케이터 \(URL\)를 현재 문서와 연결 합니다.|  
|[CDHtmlDialog::GetDHtmlDocument](../Topic/CDHtmlDialog::GetDHtmlDocument.md)|IHTMLDocument2 인터페이스에 현재 로드 된 HTML 문서를 검색합니다.|  
|[CDHtmlDialog::GetDropTarget](../Topic/CDHtmlDialog::GetDropTarget.md)|놓기 대상으로 제공 하는 대신 대화 상자를 허용 하도록 사용 하면 포함 된 WebBrowser 컨트롤에 의해 호출  [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[CDHtmlDialog::GetElement](../Topic/CDHtmlDialog::GetElement.md)|인터페이스를에서 HTML 요소를 가져옵니다.|  
|[CDHtmlDialog::GetElementHtml](../Topic/CDHtmlDialog::GetElementHtml.md)|검색 된  **innerHTML** HTML 요소의 속성입니다.|  
|[CDHtmlDialog::GetElementInterface](../Topic/CDHtmlDialog::GetElementInterface.md)|요청 된 인터페이스 포인터에서 HTML 요소를 검색합니다.|  
|[CDHtmlDialog::GetElementProperty](../Topic/CDHtmlDialog::GetElementProperty.md)|HTML 요소의 속성 값을 검색합니다.|  
|[CDHtmlDialog::GetElementText](../Topic/CDHtmlDialog::GetElementText.md)|검색 된  **innerText** HTML 요소의 속성입니다.|  
|[CDHtmlDialog::GetEvent](../Topic/CDHtmlDialog::GetEvent.md)|가져옵니다의  **IHTMLEventObj** 현재 이벤트 개체에 대 한 포인터입니다.|  
|[CDHtmlDialog::GetExternal](../Topic/CDHtmlDialog::GetExternal.md)|호스트의 `IDispatch` 인터페이스.|  
|[CDHtmlDialog::GetHostInfo](../Topic/CDHtmlDialog::GetHostInfo.md)|호스트의 UI 기능을 검색합니다.|  
|[CDHtmlDialog::GetOptionKeyPath](../Topic/CDHtmlDialog::GetOptionKeyPath.md)|사용자 기본 설정에서 저장 된 레지스트리 키를 검색 합니다.|  
|[CDHtmlDialog::HideUI](../Topic/CDHtmlDialog::HideUI.md)|호스트의 UI를 숨깁니다.|  
|[CDHtmlDialog::IsExternalDispatchSafe](../Topic/CDHtmlDialog::IsExternalDispatchSafe.md)|나타냅니다 여부 호스트의 `IDispatch` 인터페이스에 대 한 스크립팅 안전입니다.|  
|[CDHtmlDialog::LoadFromResource](../Topic/CDHtmlDialog::LoadFromResource.md)|WebBrowser 컨트롤에 지정 된 리소스를 로드합니다.|  
|[CDHtmlDialog::Navigate](../Topic/CDHtmlDialog::Navigate.md)|지정한 URL을 탐색합니다.|  
|[CDHtmlDialog::OnBeforeNavigate](../Topic/CDHtmlDialog::OnBeforeNavigate.md)|탐색 이벤트가 발생 하기 전에 프레임 워크에서 호출 됩니다.|  
|[CDHtmlDialog::OnDocumentComplete](../Topic/CDHtmlDialog::OnDocumentComplete.md)|문서에 도달 하면 응용 프로그램에 알리기 위해 프레임 워크에서 호출을 `READYSTATE_COMPLETE` 상태.|  
|[CDHtmlDialog::OnDocWindowActivate](../Topic/CDHtmlDialog::OnDocWindowActivate.md)|문서 창 활성화 또는 비활성화 되 면 프레임 워크에서 호출 됩니다.|  
|[CDHtmlDialog::OnFrameWindowActivate](../Topic/CDHtmlDialog::OnFrameWindowActivate.md)|프레임 창이 활성화 또는 비활성화 되 면 프레임 워크에서 호출 됩니다.|  
|[CDHtmlDialog::OnInitDialog](../Topic/CDHtmlDialog::OnInitDialog.md)|호출에 응답 하는  **WM\_INITDIALOG** 메시지.|  
|[CDHtmlDialog::OnNavigateComplete](../Topic/CDHtmlDialog::OnNavigateComplete.md)|탐색 이벤트를 완료 한 후 프레임 워크에 의해 호출 됩니다.|  
|[CDHtmlDialog::ResizeBorder](../Topic/CDHtmlDialog::ResizeBorder.md)|개체를 테두리 공간 크기를 조정 하는 데 필요한 경고를 보냅니다.|  
|[CDHtmlDialog::SetControlProperty](../Topic/CDHtmlDialog::SetControlProperty.md)|ActiveX 컨트롤의 속성을 새 값으로 설정합니다.|  
|[CDHtmlDialog::SetElementHtml](../Topic/CDHtmlDialog::SetElementHtml.md)|집합의  **innerHTML** HTML 요소의 속성입니다.|  
|[CDHtmlDialog::SetElementProperty](../Topic/CDHtmlDialog::SetElementProperty.md)|HTML 요소의 속성을 설정합니다.|  
|[CDHtmlDialog::SetElementText](../Topic/CDHtmlDialog::SetElementText.md)|집합의  **innerText**  HTML 요소의 속성입니다.|  
|[CDHtmlDialog::SetExternalDispatch](../Topic/CDHtmlDialog::SetExternalDispatch.md)|호스트의 설정 `IDispatch` 인터페이스.|  
|[CDHtmlDialog::SetHostFlags](../Topic/CDHtmlDialog::SetHostFlags.md)|호스트의 UI 플래그를 설정합니다.|  
|[CDHtmlDialog::ShowContextMenu](../Topic/CDHtmlDialog::ShowContextMenu.md)|상황에 맞는 메뉴가 표시 될 때 호출 됩니다.|  
|[CDHtmlDialog::ShowUI](../Topic/CDHtmlDialog::ShowUI.md)|호스트의 UI에 표시 됩니다.|  
|[CDHtmlDialog::TranslateAccelerator](../Topic/CDHtmlDialog::TranslateAccelerator.md)|메뉴 액셀러레이터 키 메시지 처리를 호출 합니다.|  
|[CDHtmlDialog::TranslateUrl](../Topic/CDHtmlDialog::TranslateUrl.md)|로드할 URL을 수정 하기 위해 호출 됩니다.|  
|[CDHtmlDialog::UpdateUI](../Topic/CDHtmlDialog::UpdateUI.md)|명령 상태가 변경 되었음을 호스트에 알리기 위해 호출 됩니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDHtmlDialog::m\_bUseHtmlTitle](../Topic/CDHtmlDialog::m_bUseHtmlTitle.md)|HTML 문서의 제목 대화 캡션으로 사용 여부를 나타냅니다.|  
|[CDHtmlDialog::m\_nHtmlResID](../Topic/CDHtmlDialog::m_nHtmlResID.md)|리소스 ID의 HTML 표시할 리소스입니다.|  
|[CDHtmlDialog::m\_pBrowserApp](../Topic/CDHtmlDialog::m_pBrowserApp.md)|웹 브라우저 응용 프로그램에 대 한 포인터입니다.|  
|[CDHtmlDialog::m\_spHtmlDoc](../Topic/CDHtmlDialog::m_spHtmlDoc.md)|HTML 문서에 대 한 포인터입니다.|  
|[CDHtmlDialog::m\_strCurrentUrl](../Topic/CDHtmlDialog::m_strCurrentUrl.md)|현재 URL입니다.|  
|[CDHtmlDialog::m\_szHtmlResID](../Topic/CDHtmlDialog::m_szHtmlResID.md)|HTML 리소스 ID의 문자열 버전|  
  
## 설명  
 **CDHtmlDialog**  는 HTML 리소스를 표시 하는 HTML 또는 URL에서 로드할 수 있습니다.  
  
 `CDHtmlDialog`또한 수행 데이터 HTML 컨트롤과 교환 및 단추 클릭 등과 같은 HTML 컨트롤에서 이벤트 처리.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CDHtmlDialog`  
  
## 요구 사항  
 **헤더:** afxdhtml.h  
  
## 참고 항목  
 [MFC 샘플 DHtmlExplore](../../top/visual-cpp-samples.md)   
 [DDX\_DHtml Helper Macros](../../mfc/reference/ddx-dhtml-helper-macros.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)