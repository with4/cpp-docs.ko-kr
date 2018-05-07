---
title: CDockState 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
dev_langs:
- C++
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fcfbe14743ffff91a4a1749f0394a6deb8f0547a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdockstate-class"></a>CDockState 클래스
영구 메모리(파일)에서 하나 이상의 도킹 컨트롤 막대의 상태를 로드, 언로드 또는 지우는 serialize된 `CObject` 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDockState : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDockState::Clear](#clear)|도킹 상태 정보를 지웁니다.|  
|[CDockState::GetVersion](#getversion)|저장 된 버전 번호를 검색 상태를 표시 합니다.|  
|[CDockState::LoadState](#loadstate)|상태 정보는 레지스트리를 검색 또는 합니다. INI 파일입니다.|  
|[CDockState::SaveState](#savestate)|레지스트리 또는 INI 파일에 상태 정보를 저장합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|저장된 된 포인터의 배열 각 컨트롤 막대에 대 한 항목을 사용 하 여 상태 정보를 도킹 합니다.|  
  
## <a name="remarks"></a>설명  
 도킹 상태 표시줄과 도킹 여부의 위치와 크기를 포함 합니다. 때 상태를 검색 하는 저장 된 도킹 `CDockState` 확인 막대의 위치 및 막대가 현재 화면 설정으로 표시 되지 않으면 `CDockState` 막대의 크기를 조정 볼 수 있도록 위치를 지정 합니다. 주요 목적은 `CDockState` 다양 한 컨트롤 막대의 전체 상태를 저장 하 고 해당 상태를 저장할 수 있도록 되 고 레지스트리에 응용 프로그램의 하나를 로드 합니다. INI 파일 또는의 일환으로 이진 형식으로는 `CArchive` 개체의 콘텐츠입니다.  
  
 막대는 도킹 가능한 컨트롤 도구 모음, 상태 표시줄, 또는 대화 상자 막대를 포함 하 여 막대 수 있습니다. `CDockState` 개체 작성 되 고 통해 파일에서 읽거나는 `CArchive` 개체입니다.  
  
 [CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) 모든 프레임 창의의 상태 정보를 검색 `CControlBar` 개체를 가져와 `CDockState` 개체입니다. 콘텐츠를 작성할 수 있습니다는 `CDockState` 개체를 사용 하 여 저장소 [Serialize](../../mfc/reference/cobject-class.md#serialize) 또는 [CDockState::SaveState](#savestate)합니다. 나중에 원하는 프레임 창에서 컨트롤 막대의 상태를 복원 하는 경우와 상태를 로드할 수 있습니다 `Serialize` 또는 [CDockState::LoadState](#loadstate)를 사용 하 여 [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) 저장 된 적용 하려면 상태 프레임 창은 컨트롤 막대입니다.  
  
 도킹 컨트롤 막대에 대 한 자세한 내용은 문서를 참조 [컨트롤 막대](../../mfc/control-bars.md), [도구 모음: 고정 및 고정 해제](../../mfc/docking-and-floating-toolbars.md), 및 [프레임 창](../../mfc/frame-windows.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxadv.h  
  
##  <a name="clear"></a>  CDockState::Clear  
 이 함수에 저장 된 모든 도킹 정보를 호출 하는 `CDockState` 개체입니다.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>설명  
 여기에 뿐만 아니라 막대 도킹, 막대의 크기와 위치를 제외한 여부 및 표시 여부.  
  
##  <a name="getversion"></a>  CDockState::GetVersion  
 저장 된 버전 번호를 검색 하려면이 함수 호출 상태를 표시 합니다.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>반환 값  
 이면 1 저장된 표시줄 정보 보다 오래 된 상태 이면 막대 현재 경우 2 저장된 표시줄 정보는 현재와 동일 상태 모음입니다.  
  
### <a name="remarks"></a>설명  
 버전 지원을 통해 수정 된 막대를를 새 영구적 속성을 추가 하 고 계속 검색 하 고 막대의 이전 버전에서 만든 영구 상태를 로드 하는 작업을 할 수 있습니다.  
  
##  <a name="loadstate"></a>  CDockState::LoadState  
 레지스트리에서 상태 정보를 검색 하려면이 함수를 호출 하거나 합니다. INI 파일입니다.  
  
```  
void LoadState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszProfileName`  
 초기화 파일 또는 상태 정보가 저장 되어 있는 Windows 레지스트리에서 키에 있는 섹션의 이름을 지정 하는 null teminated 문자열을 가리킵니다.  
  
### <a name="remarks"></a>설명  
 프로필 이름은 응용 프로그램의 섹션입니다. INI 파일 또는 레지스트리 막대의 상태 정보를 포함 합니다. 컨트롤 막대 상태 정보를 레지스트리에 저장할 수 있습니다 또는 합니다. INI 파일을 `SaveState`합니다.  
  
##  <a name="m_arrbarinfo"></a>  CDockState::m_arrBarInfo  
 A `CPtrArray` 에서 상태 정보 저장에 각 컨트롤 막대에 대 한 저장된 컨트롤 막대 정보에 대 한 포인터의 배열인 개체는 `CDockState` 개체입니다.  
  
```  
CPtrArray m_arrBarInfo;  
```  
  
##  <a name="savestate"></a>  CDockState::SaveState  
 레지스트리에 상태 정보를 저장 하려면이 함수를 호출 하거나 합니다. INI 파일입니다.  
  
```  
void SaveState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszProfileName`  
 초기화 파일 또는 상태 정보가 저장 되어 있는 Windows 레지스트리에서 키에 있는 섹션의 이름을 지정 하는 null teminated 문자열을 가리킵니다.  
  
### <a name="remarks"></a>설명  
 프로필 이름은 응용 프로그램의 섹션입니다. 포함 된 INI 파일 또는 레지스트리 컨트롤 막대의 상태 정보입니다. `SaveState` 또한 현재 화면 크기를 저장합니다. 레지스트리에서 컨트롤 모음 정보를 검색할 수 있습니다 또는 합니다. INI 파일을 `LoadState`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)

