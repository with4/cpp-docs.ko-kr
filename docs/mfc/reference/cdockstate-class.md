---
title: "CDockState 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockState
dev_langs:
- C++
helpviewer_keywords:
- dock state
- size
- docking control bars
- CDockState class
- states, dockable control bar
- position, control bar
- size, control bar
- docking tool windows
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fc8beb80cc35c1816fbc305ece2bfbc5df2e7cd0
ms.lasthandoff: 02/24/2017

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
|[CDockState::GetVersion](#getversion)|저장 된 버전 번호를 검색 합니다. 상태 표시줄입니다.|  
|[CDockState::LoadState](#loadstate)|검색에서에서 상태 정보를 레지스트리 또는 합니다. INI 파일입니다.|  
|[CDockState::SaveState](#savestate)|레지스트리 또는 INI 파일에 상태 정보를 저장합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|저장 된 포인터의 배열에는 각 컨트롤 막대에 대 한 항목이 있는 상태 정보를 도킹 합니다.|  
  
## <a name="remarks"></a>주의  
 도킹 상태 표시줄과 도킹 여부의 위치와 크기를 포함 합니다. 때 상태를 저장 된 검색 도킹 `CDockState` 막대의 검사 위치 및 막대 현재 화면 설정으로 표시 되지 않으면 `CDockState` 막대의 크기를 조정할 위치를 볼 수 있도록 합니다. 주요 목적은 `CDockState` 다양 한 컨트롤 막대의 전체 상태를 저장 하 고 해당 상태를 저장할 수 있도록 하 고 레지스트리의 응용 프로그램을 로드 합니다. INI 파일의 또는의 일환으로 이진 형식으로는 `CArchive` 개체의 콘텐츠입니다.  
  
 막대는 도킹 가능한 모든 컨트롤 막대, 도구 모음, 상태 표시줄 또는 대화 상자 막대를 포함 하 여 수 있습니다. `CDockState`개체를 작성 하 고 통해 파일에서 읽거나는 `CArchive` 개체입니다.  
  
 [CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) 모든 프레임 창의의 상태 정보를 검색 `CControlBar` 개체를 가져와 `CDockState` 개체입니다. 콘텐츠를 작성할 수 있습니다는 `CDockState` 개체와 함께 저장소를 [Serialize](../../mfc/reference/cobject-class.md#serialize) 또는 [CDockState::SaveState](#savestate)합니다. 나중에 프레임 창에서 컨트롤 막대의 상태를 복원 하려면 포함 하 여 상태를 로드할 수 있습니다 `Serialize` 또는 [CDockState::LoadState](#loadstate), 사용 하 여 [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) 프레임 창은 컨트롤 막대에 저장된 된 상태를 적용할 수 있습니다.  
  
 도킹 컨트롤 막대에 대 한 자세한 내용은 문서를 참조 [컨트롤 막대](../../mfc/control-bars.md), [도구 모음: 고정 및 고정 해제](../../mfc/docking-and-floating-toolbars.md), 및 [프레임 창](../../mfc/frame-windows.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxadv.h  
  
##  <a name="a-namecleara--cdockstateclear"></a><a name="clear"></a>CDockState::Clear  
 이 함수에 저장 된 모든 도킹 정보를 호출 하는 `CDockState` 개체입니다.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>주의  
 뿐만 아니라 막대 도킹 여부 막대의 크기와 위치를 제외한 여부 및 표시 여부 포함 됩니다.  
  
##  <a name="a-namegetversiona--cdockstategetversion"></a><a name="getversion"></a>CDockState::GetVersion  
 저장 된 버전 번호를 검색 하려면이 함수를 호출 합니다. 상태 표시줄입니다.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>반환 값  
 1이 저장된 표시줄 상태 표시줄 현재 보다 오래 된 정보는 경우 2 저장된 모음 정보는 현재와 동일 하 게 상태 표시줄입니다.  
  
### <a name="remarks"></a>주의  
 버전 지원을 통해 수정 된 막대를 새 영구 속성을 추가 하 고 계속 감지 하 여 막대의 이전 버전에서 만든 영구 상태를 로드할 수 있습니다.  
  
##  <a name="a-nameloadstatea--cdockstateloadstate"></a><a name="loadstate"></a>CDockState::LoadState  
 레지스트리에서 상태 정보를 검색 하려면이 함수를 호출 하거나. INI 파일입니다.  
  
```  
void LoadState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszProfileName`  
 초기화 파일 또는 상태 정보가 저장 되어 있는 Windows 레지스트리에서 키에 있는 섹션의 이름을 지정 하는 null teminated 문자열을 가리킵니다.  
  
### <a name="remarks"></a>주의  
 프로필 이름은 응용 프로그램의 섹션입니다. INI 파일 또는 레지스트리 막대의 상태 정보를 포함 합니다. 레지스트리를 제어 표시줄 상태 정보를 저장할 수 또는 합니다. INI 파일을 `SaveState`합니다.  
  
##  <a name="a-namemarrbarinfoa--cdockstatemarrbarinfo"></a><a name="m_arrbarinfo"></a>CDockState::m_arrBarInfo  
 A `CPtrArray` 가 상태 정보를 저장 하는 각 컨트롤 막대에 대 한 저장된 컨트롤 막대 정보에 대 한 포인터의 배열인 개체는 `CDockState` 개체입니다.  
  
```  
CPtrArray m_arrBarInfo;  
```  
  
##  <a name="a-namesavestatea--cdockstatesavestate"></a><a name="savestate"></a>CDockState::SaveState  
 레지스트리에 상태 정보를 저장 하려면이 함수를 호출 하거나. INI 파일입니다.  
  
```  
void SaveState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszProfileName`  
 초기화 파일 또는 상태 정보가 저장 되어 있는 Windows 레지스트리에서 키에 있는 섹션의 이름을 지정 하는 null teminated 문자열을 가리킵니다.  
  
### <a name="remarks"></a>주의  
 프로필 이름은 응용 프로그램의 섹션입니다. 포함 된 INI 파일이 나 레지스트리 컨트롤 막대의 상태 정보입니다. `SaveState`또한 현재 화면 크기를 저장합니다. 레지스트리에서 컨트롤 모음 정보를 검색할 수 또는 합니다. INI 파일을 `LoadState`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)


