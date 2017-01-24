---
title: "IOleObjectImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IOleObjectImpl"
  - "ATL.IOleObjectImpl<T>"
  - "ATL::IOleObjectImpl"
  - "ATL::IOleObjectImpl<T>"
  - "IOleObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], communication between container and control"
  - "IOleObject, ATL 구현"
  - "IOleObjectImpl class"
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IOleObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  **IUnknown** 및 컨테이너 통신 컨트롤을 통해 사용자 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IOleObjectImpl :  
public IOleObject  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IOleObjectImpl`.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IOleObjectImpl::Advise](../Topic/IOleObjectImpl::Advise.md)|컨트롤에 권장 되는 연결을 설정합니다.|  
|[IOleObjectImpl::Close](../Topic/IOleObjectImpl::Close.md)|로드 된 실행에서 컨트롤 상태를 변경 합니다.|  
|[IOleObjectImpl::DoVerb](../Topic/IOleObjectImpl::DoVerb.md)|해당 열거 작업 중 하나를 수행 하도록 컨트롤에 지시 합니다.|  
|[IOleObjectImpl::DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md)|컨트롤 활성 상태가 유지 됩니다 알 수 있습니다.|  
|[IOleObjectImpl::DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md)|사용자 인터페이스의 보기에서 제거 하려면 컨트롤을 지시 합니다.|  
|[IOleObjectImpl::DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md)|컨트롤을 실행 하 고 해당 창을 설치 컨트롤의 사용자 인터페이스를 설치 하지 않습니다.|  
|[IOleObjectImpl::DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md)|별도 창에서 열기 편집 컨트롤이 됩니다.|  
|[IOleObjectImpl::DoVerbPrimary](../Topic/IOleObjectImpl::DoVerbPrimary.md)|컨트롤을 두 번 클릭할 때 지정 된 동작을 수행 합니다.  컨트롤은 일반적으로 컨트롤 내부 활성화 동작을 정의 합니다.|  
|[IOleObjectImpl::DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md)|새로 삽입된 하는 컨트롤 사용자에 게 표시 됩니다.|  
|[IOleObjectImpl::DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md)|컨트롤 원위치 활성화 되 고 메뉴 및 도구 모음과 같은 컨트롤의 사용자 인터페이스를 보여 줍니다.|  
|[IOleObjectImpl::EnumAdvise](../Topic/IOleObjectImpl::EnumAdvise.md)|컨트롤의 advise 연결을 열거합니다.|  
|[IOleObjectImpl::EnumVerbs](../Topic/IOleObjectImpl::EnumVerbs.md)|컨트롤에 대 한 작업을 열거합니다.|  
|[IOleObjectImpl::GetClientSite](../Topic/IOleObjectImpl::GetClientSite.md)|컨트롤의 클라이언트 사이트를 검색합니다.|  
|[IOleObjectImpl::GetClipboardData](../Topic/IOleObjectImpl::GetClipboardData.md)|클립보드에서 데이터를 검색합니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IOleObjectImpl::GetExtent](../Topic/IOleObjectImpl::GetExtent.md)|컨트롤의 표시 영역의 범위를 검색합니다.|  
|[IOleObjectImpl::GetMiscStatus](../Topic/IOleObjectImpl::GetMiscStatus.md)|컨트롤의 상태를 검색합니다.|  
|[IOleObjectImpl::GetMoniker](../Topic/IOleObjectImpl::GetMoniker.md)|컨트롤의 모니커를 검색합니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IOleObjectImpl::GetUserClassID](../Topic/IOleObjectImpl::GetUserClassID.md)|컨트롤의 클래스 식별자를 검색합니다.|  
|[IOleObjectImpl::GetUserType](../Topic/IOleObjectImpl::GetUserType.md)|컨트롤의 사용자 형식 이름을 검색합니다.|  
|[IOleObjectImpl::InitFromData](../Topic/IOleObjectImpl::InitFromData.md)|컨트롤에서 선택된 된 데이터를 초기화합니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IOleObjectImpl::IsUpToDate](../Topic/IOleObjectImpl::IsUpToDate.md)|컨트롤 최신 인지 확인 합니다.  ATL 구현을 반환 `S_OK`.|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](../Topic/IOleObjectImpl::OnPostVerbDiscardUndo.md)|호출 하  [DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md) 실행 취소 상태를 삭제 한 후.|  
|[IOleObjectImpl::OnPostVerbHide](../Topic/IOleObjectImpl::OnPostVerbHide.md)|호출 하  [DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md) 컨트롤이 숨겨진 후.|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](../Topic/IOleObjectImpl::OnPostVerbInPlaceActivate.md)|호출 하  [DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md) 컨트롤에서 활성화 된 후.|  
|[IOleObjectImpl::OnPostVerbOpen](../Topic/IOleObjectImpl::OnPostVerbOpen.md)|호출 하  [DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md) 컨트롤을 별도 창에서 편집을 위해 연 후.|  
|[IOleObjectImpl::OnPostVerbShow](../Topic/IOleObjectImpl::OnPostVerbShow.md)|호출 하  [DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md) 컨트롤 표시 후.|  
|[IOleObjectImpl::OnPostVerbUIActivate](../Topic/IOleObjectImpl::OnPostVerbUIActivate.md)|호출 하  [DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md) 컨트롤의 사용자 인터페이스를 활성화 하면 됩니다.|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](../Topic/IOleObjectImpl::OnPreVerbDiscardUndo.md)|호출 하  [DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md) 전에 실행 취소 상태가 취소 됩니다.|  
|[IOleObjectImpl::OnPreVerbHide](../Topic/IOleObjectImpl::OnPreVerbHide.md)|호출 하  [DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md) 컨트롤을 숨기기 전에.|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](../Topic/IOleObjectImpl::OnPreVerbInPlaceActivate.md)|호출 하  [DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md) 컨트롤의 현재 위치에서 활성화 되기 전에.|  
|[IOleObjectImpl::OnPreVerbOpen](../Topic/IOleObjectImpl::OnPreVerbOpen.md)|호출 하  [DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md) 컨트롤을 별도 창에서 편집을 위해 열려 전에.|  
|[IOleObjectImpl::OnPreVerbShow](../Topic/IOleObjectImpl::OnPreVerbShow.md)|호출 하  [DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md) 컨트롤 표시 했습니다 전에.|  
|[IOleObjectImpl::OnPreVerbUIActivate](../Topic/IOleObjectImpl::OnPreVerbUIActivate.md)|호출 하  [DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md) 컨트롤의 사용자 인터페이스를 활성화 된 전에.|  
|[IOleObjectImpl::SetClientSite](../Topic/IOleObjectImpl::SetClientSite.md)|컨트롤의 클라이언트 사이트 컨테이너에 대 한 알 수 있습니다.|  
|[IOleObjectImpl::SetColorScheme](../Topic/IOleObjectImpl::SetColorScheme.md)|색 구성표를 있을 경우 컨트롤의 응용 프로그램에 것이 좋습니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IOleObjectImpl::SetExtent](../Topic/IOleObjectImpl::SetExtent.md)|컨트롤의 표시 영역의 범위를 설정합니다.|  
|[IOleObjectImpl::SetHostNames](../Topic/IOleObjectImpl::SetHostNames.md)|컨트롤 및 컨테이너 문서 컨테이너 응용 프로그램의 이름을 알 수 있습니다.|  
|[IOleObjectImpl::SetMoniker](../Topic/IOleObjectImpl::SetMoniker.md)|컨트롤 이란 해당 모니커를 알려 줍니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IOleObjectImpl::Unadvise](../Topic/IOleObjectImpl::Unadvise.md)|권장 되는 연결 컨트롤을 삭제합니다.|  
|[IOleObjectImpl::Update](../Topic/IOleObjectImpl::Update.md)|컨트롤을 업데이트합니다.  ATL 구현을 반환 `S_OK`.|  
  
## 설명  
 [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) 인터페이스 컨테이너 통신 컨트롤을 통해 사용자 인터페이스입니다.  클래스 `IOleObjectImpl` 는이 인터페이스의 기본 구현을 제공 하 고 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Class Overview](../../atl/atl-class-overview.md)