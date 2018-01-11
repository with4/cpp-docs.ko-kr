---
title: "CUserToolsManager 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CreateNewTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::FindTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetArgumentsMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetFilter
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetInitialDirMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetMaxTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetToolsEntryCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetUserTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::InvokeTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::IsUserToolCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::LoadState
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolDown
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolUp
- AFXUSERTOOLSMANAGER/CUserToolsManager::RemoveTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::SaveState
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetFilter
dev_langs: C++
helpviewer_keywords:
- CUserToolsManager [MFC], CUserToolsManager
- CUserToolsManager [MFC], CreateNewTool
- CUserToolsManager [MFC], FindTool
- CUserToolsManager [MFC], GetArgumentsMenuID
- CUserToolsManager [MFC], GetDefExt
- CUserToolsManager [MFC], GetFilter
- CUserToolsManager [MFC], GetInitialDirMenuID
- CUserToolsManager [MFC], GetMaxTools
- CUserToolsManager [MFC], GetToolsEntryCmd
- CUserToolsManager [MFC], GetUserTools
- CUserToolsManager [MFC], InvokeTool
- CUserToolsManager [MFC], IsUserToolCmd
- CUserToolsManager [MFC], LoadState
- CUserToolsManager [MFC], MoveToolDown
- CUserToolsManager [MFC], MoveToolUp
- CUserToolsManager [MFC], RemoveTool
- CUserToolsManager [MFC], SaveState
- CUserToolsManager [MFC], SetDefExt
- CUserToolsManager [MFC], SetFilter
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d92e0ffa11ea07331704bfcd91798c50c48dabac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cusertoolsmanager-class"></a>CUserToolsManager 클래스
컬렉션을 유지 [CUserTool 클래스](../../mfc/reference/cusertool-class.md) 응용 프로그램의 개체입니다. 사용자 도구는 외부 응용 프로그램을 실행하는 메뉴 항목입니다. `CUserToolsManager` 개체를 사용하면 사용자 또는 개발자가 응용 프로그램에 새 사용자 도구를 추가할 수 있습니다. 사용자 도구와 연결된 명령 실행을 지원하고 사용자 도구에 관한 정보를 Windows 레지스트리를 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CUserToolsManager : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|`CUserToolsManager`를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CUserToolsManager::CreateNewTool](#createnewtool)|새 사용자 도구를 만듭니다.|  
|[CUserToolsManager::FindTool](#findtool)|에 대 한 포인터를 반환 합니다.는 `CMFCUserTool` 는 지정한 명령 ID와 연결 된 개체|  
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|연결 된 리소스 ID를 반환는 **인수** 메뉴에는 **도구** 탭은 **사용자 지정** 대화 상자.|  
|[CUserToolsManager::GetDefExt](#getdefext)|기본 확장 프로그램을 반환 합니다는 **파일 열기** 대화 상자 ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog))에서 사용 하 여는 **명령** 필드에 **도구** 탭에는 **사용자 지정** 대화 상자.|  
|[CUserToolsManager::GetFilter](#getfilter)|파일 필터를 반환는 **파일 열기** 대화 상자 ( [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md))에서 사용 하 여는 **명령** 필드에 **도구** 탭에는 **사용자 지정** 대화 상자.|  
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|연결 된 리소스 ID를 반환는 **초기 디렉터리** 메뉴에는 **도구** 탭은 **사용자 지정** 대화 상자.|  
|[CUserToolsManager::GetMaxTools](#getmaxtools)|응용 프로그램에 할당 될 수 있는 사용자 도구의 최대 수를 반환 합니다.|  
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|사용자 도구에 대 한 메뉴 항목 자리 표시자의 명령 ID를 반환합니다.|  
|[CUserToolsManager::GetUserTools](#getusertools)|사용자 도구 목록에 대 한 참조를 반환합니다.|  
|[CUserToolsManager::InvokeTool](#invoketool)|Id가 지정 된 명령 ID를 가진 사용자 도구와 연결 된 응용 프로그램 실행|  
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|명령 ID는 사용자 도구와 연결 인지 확인 합니다.|  
|[CUserToolsManager::LoadState](#loadstate)|Windows 레지스트리에서 사용자 도구에 대 한 정보를 로드합니다.|  
|[CUserToolsManager::MoveToolDown](#movetooldown)|지정 된 사용자 도구를 사용자 도구 목록에서 아래로 이동합니다.|  
|[CUserToolsManager::MoveToolUp](#movetoolup)|지정 된 사용자 도구를 사용자 도구 목록에서 위로 이동합니다.|  
|[CUserToolsManager::RemoveTool](#removetool)|응용 프로그램에서 사용자 지정된 도구를 제거합니다.|  
|[CUserToolsManager::SaveState](#savestate)|Windows 레지스트리에 사용자 도구에 대 한 정보를 저장합니다.|  
|[CUserToolsManager::SetDefExt](#setdefext)|기본 확장명을 지정 하는 **파일 열기** 대화 상자 ( [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md))에서 사용 하 여는 **명령** 필드에 **도구** 탭 **사용자 지정** 대화 상자.|  
|[CUserToolsManager::SetFilter](#setfilter)|파일을 필터링 하는 **파일 열기** 대화 상자 ( [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md))에서 사용 하 여는 **명령** 필드에 **도구** 탭에는 **사용자 지정** 대화 상자.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램에 사용자 도구를 통합 하려면 다음을 수행 해야 합니다.  
  
 1. 메뉴 항목 및 사용자 도구 메뉴 항목에 대 한 연결 된 명령 ID를 예약 합니다.  
  
 2. 사용자가 응용 프로그램에서 정의할 수 있는 각 사용자 도구에 대 한 순차적 명령 ID를 예약 합니다.  
  
 3. 호출 된 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) 메서드 다음 매개 변수를 지정 하 고: 메뉴 명령 ID, 첫 번째 사용자 도구 명령 ID 및 마지막 사용자 도구 명령 ID  
  
 있어야 하나만 글로벌 `CUserToolsManager` 응용 프로그램당 개체입니다.  
  
 예를 보려면 사용자 도구 VisualStudioDemo 샘플 프로젝트를 참조 합니다.  
  
## <a name="example"></a>예  
 다음 예제에 대 한 참조를 검색 하는 방법을 보여 줍니다는 `CUserToolsManager` 를 새 사용자 도구를 만드는 방법과 개체입니다. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CUserToolsManager`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxusertoolsmanager.h  
  
##  <a name="createnewtool"></a>CUserToolsManager::CreateNewTool  
 새 사용자 도구를 만듭니다.  
  
```  
CUserTool* CreateNewTool();
```  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 사용자 도구에 대 한 포인터 또는 `NULL` 사용자 도구 수가 최대값을 초과 하는 경우. 반환 되는 형식은 형식에 전달 되는 것과 같습니다 `CWinAppEx::EnableUserTools` 로 `pToolRTC` 매개 변수입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드 호출에 제공 되는 범위에서 첫 번째 사용 가능한 메뉴 명령 ID를 찾아 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) 사용자 도구가이 ID를 할당 하 고  
  
 메서드가 도구 수가 최대값에 도달한 경우 실패 합니다. 사용자 도구에는 범위 내의 모든 명령 Id를 할당 하면 발생 합니다. 호출 하 여 도구의 최대 수를 검색할 수 있습니다 [CUserToolsManager::GetMaxTools](#getmaxtools)합니다. 호출 하 여 도구 목록에 대 한 액세스를 얻을 수는 [CUserToolsManager::GetUserTools](#getusertools) 메서드.  
  
##  <a name="cusertoolsmanager"></a>CUserToolsManager::CUserToolsManager  
 `CUserToolsManager`를 생성합니다. 각 응용 프로그램에는 최대 하나의 사용자 도구 관리자를 있어야 합니다.  
  
```  
CUserToolsManager();

 
CUserToolsManager(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID=0,  
    UINT uInitDirMenuID=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdToolsDummy`  
 프레임 워크 사용자 도구 메뉴의 명령 ID에 대 한 자리 표시자로 사용 하는 부호 없는 정수입니다.  
  
 [in] `uiCmdFirst`  
 첫 번째 사용자 도구 명령에 대 한 명령 ID입니다.  
  
 [in] `uiCmdLast`  
 마지막 사용자 도구 명령에 대 한 명령 ID입니다.  
  
 [in] `pToolRTC`  
 클래스는 [CUserToolsManager::CreateNewTool](#createnewtool) 만듭니다. 이 클래스를 사용 하 여의 파생된 형식에 사용할 수 있습니다 [CUserTool 클래스](../../mfc/reference/cusertool-class.md) 기본 구현 대신 합니다.  
  
 [in] `uArgMenuID`  
 인수 팝업 메뉴의 메뉴 리소스 ID입니다.  
  
 [in] `uInitDirMenuID`  
 초기 디렉터리 팝업 메뉴의 메뉴 리소스 ID입니다.  
  
### <a name="remarks"></a>설명  
 이 생성자를 호출 하지 마십시오. 대신, 호출 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) 사용 사용자 도구 및 호출 [CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) 에 대 한 포인터를 가져올 수는 `CUserToolsManager`합니다. 자세한 내용은 참조 [사용자 정의 도구](../../mfc/user-defined-tools.md)합니다.  
  
##  <a name="findtool"></a>CUserToolsManager::FindTool  
 에 대 한 포인터를 반환 합니다.는 [CUserTool 클래스](../../mfc/reference/cusertool-class.md) 는 지정한 명령 ID와 연결 된 개체  
  
```  
CUserTool* FindTool(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdId`  
 메뉴 명령 식별자입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CUserTool 클래스](../../mfc/reference/cusertool-class.md) 또는 `CUserTool`-파생 하는 경우 개체 성공 하지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 때 `FindTool` 가 성공적으로 반환 되는 형식은 같습니다의 형식으로는 `pToolRTC` 매개 변수를 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)합니다.  
  
##  <a name="getargumentsmenuid"></a>CUserToolsManager::GetArgumentsMenuID  
 연결 된 리소스 ID를 반환는 **인수** 메뉴에는 **도구** 탭은 **사용자 지정** 대화 상자.  
  
```  
UINT GetArgumentsMenuID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 메뉴 리소스의 식별자입니다.  
  
### <a name="remarks"></a>설명  
 `uArgMenuID` 의 매개 변수 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) 리소스의 ID를 지정 합니다.  
  
##  <a name="getdefext"></a>CUserToolsManager::GetDefExt  
 기본 확장 프로그램을 반환 합니다는 **파일 열기** 대화 상자 ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog))에서 사용 하 여는 **명령** 필드에 **도구** 탭에는 **사용자 지정** 대화 상자.  
  
```  
const CString& GetDefExt() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조는 `CString` 확장을 포함 하는 개체입니다.  
  
##  <a name="getfilter"></a>CUserToolsManager::GetFilter  
 파일 필터를 반환는 **파일 열기** 대화 상자 ( [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md))에서 사용 하 여는 **명령** 필드에 **도구** 탭에는 **사용자 지정** 대화 상자.  
  
```  
const CString& GetFilter() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조는 `CString` 필터가 포함 된 개체입니다.  
  
##  <a name="getinitialdirmenuid"></a>CUserToolsManager::GetInitialDirMenuID  
 연결 된 리소스 ID를 반환는 **초기 디렉터리** 메뉴에는 **도구** 탭은 **사용자 지정** 대화 상자.  
  
```  
UINT GetInitialDirMenuID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 메뉴 리소스 식별자입니다.  
  
### <a name="remarks"></a>설명  
 반환된 된 ID에 지정 된 된 `uInitDirMenuID` 의 매개 변수 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)합니다.  
  
##  <a name="getmaxtools"></a>CUserToolsManager::GetMaxTools  
 응용 프로그램에 할당 될 수 있는 사용자 도구의 최대 수를 반환 합니다.  
  
```  
int GetMaxTools() const;  
```  
  
### <a name="return-value"></a>반환 값  
 사용자 도구 할당 될 수 있는 최대 수입니다.  
  
### <a name="remarks"></a>설명  
 응용 프로그램에 할당 될 수 있는 도구의 최대 수를 검색 하려면이 메서드를 호출 합니다. 이 숫자는 범위에 Id 수는 `uiCmdFirst` 통해는 `uiCmdLast` 매개 변수를 전달 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)합니다.  
  
##  <a name="gettoolsentrycmd"></a>CUserToolsManager::GetToolsEntryCmd  
 사용자 도구에 대 한 메뉴 항목 자리 표시자의 명령 ID를 반환합니다.  
  
```  
UINT GetToolsEntryCmd() const;  
```  
  
### <a name="return-value"></a>반환 값  
 자리 표시자의 명령 ID입니다.  
  
### <a name="remarks"></a>설명  
 호출 하면 사용자 도구를 사용 하려면 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)합니다. `uiCmdToolsDummy` 매개 변수는 도구 항목 명령의 명령 ID를 지정 합니다. 이 메서드가 반환 도구 항목 명령 id입니다. 메뉴에 해당 ID를 사용 하는 경우 항상 메뉴가 나타나면 사용자 도구 목록은 대체 될 합니다.  
  
##  <a name="getusertools"></a>CUserToolsManager::GetUserTools  
 사용자 도구 목록에 대 한 참조를 반환합니다.  
  
```  
const CObList& GetUserTools() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 const 참조는 [CObList 클래스](../../mfc/reference/coblist-class.md) 도구 사용자의 목록을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 호출 되는 도구 사용자의 목록을 검색 하려면이 메서드는 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) 개체를 유지 관리 합니다. 각 사용자 도구는 형식의 개체를 나타내는 [CUserTool 클래스](../../mfc/reference/cusertool-class.md) 에서 파생 된 유형 또는 `CUserTool`합니다. 지정 된 형식에서 `pToolRTC` 를 호출할 때 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) 사용자 도구를 사용 하도록 설정 하려면.  
  
##  <a name="invoketool"></a>CUserToolsManager::InvokeTool  
 Id가 지정 된 명령 ID를 가진 사용자 도구와 연결 된 응용 프로그램 실행  
  
```  
BOOL InvokeTool(UINT uiCmdId);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdId`  
 사용자 도구와 연결 된 메뉴 명령 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 사용자 도구와 연결 된 명령이 성공적으로 실행 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용자와 연결 된 응용 프로그램을 실행 하는 도구는 호출에 의해 지정 된 명령 ID `uiCmdId`합니다.  
  
##  <a name="isusertoolcmd"></a>CUserToolsManager::IsUserToolCmd  
 명령 ID는 사용자 도구와 연결 인지 확인 합니다.  
  
```  
BOOL IsUserToolCmd(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdId`  
 메뉴 항목의 명령 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 지정한 명령 ID는 사용자 도구; 연관 된 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 지정한 명령 ID가 명령 ID 범위에 있는지 여부를 확인 합니다. 호출 하는 경우 범위 지정 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) 사용자 도구를 사용 하도록 합니다.  
  
##  <a name="loadstate"></a>CUserToolsManager::LoadState  
 Windows 레지스트리에서 사용자 도구에 대 한 정보를 로드합니다.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 Windows 레지스트리 키의 경로입니다.  
  
### <a name="return-value"></a>반환 값  
 상태를 성공적으로 로드 한 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 상태를 로드 하는이 메서드는 `CUserToolsManager` Windows 레지스트리에서 개체입니다.  
  
 일반적으로 호출 하지 않으면이 메서드 직접 합니다. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) 작업 영역 초기화 프로세스의 일환으로 호출 합니다.  
  
##  <a name="movetooldown"></a>CUserToolsManager::MoveToolDown  
 지정 된 사용자 도구를 사용자 도구 목록에서 아래로 이동합니다.  
  
```  
BOOL MoveToolDown(CUserTool* pTool);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pTool`  
 이동 하 고 사용자 도구를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 사용자 도구를 아래로 이동 되었으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 메서드가 실패 하는 경우 도구는는 `pTool` 지정 내부 목록에 없는 경우이 도구는 목록에서 마지막 또는 합니다.  
  
##  <a name="movetoolup"></a>CUserToolsManager::MoveToolUp  
 지정 된 사용자 도구를 사용자 도구 목록에서 위로 이동합니다.  
  
```  
BOOL MoveToolUp(CUserTool* pTool);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pTool`  
 이동 하 고 사용자 도구를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 사용자 도구 성공적으로 이동 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 메서드가 실패 하는 경우 도구는는 `pTool` 내부 목록에 없는 매개 변수 지정 또는 도구는 첫 번째 도구 항목 목록에 없는 경우.  
  
##  <a name="removetool"></a>CUserToolsManager::RemoveTool  
 응용 프로그램에서 사용자 지정된 도구를 제거합니다.  
  
```  
BOOL RemoveTool(CUserTool* pTool);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `pTool`  
 제거할 사용자 도구에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도구는 성공적으로 제거 됩니다. 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 삭제 하는 도구를 성공적으로 제거 하면 `pTool`합니다.  
  
##  <a name="savestate"></a>CUserToolsManager::SaveState  
 Windows 레지스트리에 사용자 도구에 대 한 정보를 저장합니다.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 Windows 레지스트리 키 경로입니다.  
  
### <a name="return-value"></a>반환 값  
 상태 저장 했습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 현재 상태를 저장 하는 메서드는 `CUserToolsManager` Windows 레지스트리에 있는 개체입니다.  
  
 이 메서드를 직접 호출할 필요가 없습니다 일반적으로 [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) 응용 프로그램의 작업 영역 serialization 프로세스의 일부로 자동으로 호출 합니다.  
  
##  <a name="setdefext"></a>CUserToolsManager::SetDefExt  
 기본 확장명을 지정 하는 **파일 열기** 대화 상자 ( [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md))에서 사용 하 여는 **명령** 필드에 **도구** 탭 **사용자 지정** 대화 상자.  
  
```  
void SetDefExt(const CString& strDefExt);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strDefExt`  
 기본 파일 이름 확장명을 포함 하는 텍스트 문자열입니다.  
  
### <a name="remarks"></a>설명  
 기본 파일 이름 확장명을 지정 하려면이 메서드를 호출 하는 **파일 열기** 사용자 도구에 연결 하는 응용 프로그램을 선택할 때 표시 되는 대화 상자. 기본값은 "exe".  
  
##  <a name="setfilter"></a>CUserToolsManager::SetFilter  
 파일을 필터링 하는 **파일 열기** 대화 상자 ( [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md))에서 사용 하 여는 **명령** 필드에 **도구** 탭에는 **사용자 지정** 대화 상자.  
  
```  
void SetFilter(const CString& strFilter);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strFilter`  
 필터를 지정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)   
 [CUserTool 클래스](../../mfc/reference/cusertool-class.md)
