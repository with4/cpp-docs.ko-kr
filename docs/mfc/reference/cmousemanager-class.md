---
title: "CMouseManager 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
dev_langs: C++
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f50b74731089346a9675b5340ba0ea1a0b2879f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmousemanager-class"></a>CMouseManager 클래스
사용자가 다양 한 명령어를 특정 연결 하도록 허용 [CView](../../mfc/reference/cview-class.md) 사용자가 뷰 안에서 두 번 클릭할 때 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMouseManager : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMouseManager::AddView](#addview)|추가 `CView` 개체는 **사용자 지정** 대화 상자. **사용자 지정** 대화 상자에서는 사용자를 두 번 클릭을 각 나열된 된 보기에 대 한 명령을 사용 하 여 연결 합니다.|  
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|사용자 제공된 뷰 안에서 두 번 클릭할 때 실행 되는 명령을 반환 합니다.|  
|[CMouseManager::GetViewIconId](#getviewiconid)|제공 된 보기 ID와 연결 된 아이콘을 반환 합니다.|  
|[CMouseManager::GetViewIdByName](#getviewidbyname)|제공 된 뷰 이름과 연결 된 뷰 ID를 반환 합니다.|  
|[CMouseManager::GetViewNames](#getviewnames)|모든 추가 된 뷰 이름의 목록을 검색합니다.|  
|[CMouseManager::LoadState](#loadstate)|로드는 `CMouseManager` Windows 레지스트리에서 상태입니다.|  
|[CMouseManager::SaveState](#savestate)|기록 된 `CMouseManager` Windows 레지스트리에 상태입니다.|  
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|제공된 된 명령 및 제공 된 보기에 연결합니다.|  
  
## <a name="remarks"></a>설명  
 `CMouseManager` 클래스의 컬렉션을 유지 `CView` 개체입니다. 각 보기 ID 및 이름으로 식별 됩니다. 이러한 보기에 표시 되는 **사용자 지정** 대화 상자. 명령을 통해 모든 보기와 연결 된 사용자를 변경할 수는 **사용자 지정** 대화 상자. 사용자가 해당 보기에는 관련 된 명령이 실행 됩니다. 이 코딩 관점에서에서 지원 하려면 처리 해야는 `WM_LBUTTONDBLCLK` 메시지 및 통화는 [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) 의 코드에서 함수 `CView` 개체...  
  
 만들지 마십시오는 `CMouseManager` 수동으로 개체입니다. 응용 프로그램의 프레임 워크에 의해 생성 됩니다. 사용자가 응용 프로그램을 종료할 때 자동으로 소멸도 됩니다. 응용 프로그램에 대 한 마우스 관리자에 대 한 포인터를 가져오려면, 호출 [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMouseManager`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmousemanager.h  
  
##  <a name="addview"></a>CMouseManager::AddView  
 등록 한 [CView](../../mfc/reference/cview-class.md) 개체는 [CMouseManager 클래스](../../mfc/reference/cmousemanager-class.md) 마우스 사용자 지정 동작을 지원 합니다.  
  
```  
BOOL AddView(
    int iViewId,  
    UINT uiViewNameResId,  
    UINT uiIconId = 0);

 
BOOL AddView(
    int iId,  
    LPCTSTR lpszViewName,  
    UINT uiIconId = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iViewId`  
 뷰 id입니다.  
  
 [in] `uiViewNameResId`  
 뷰 이름을 참조 하는 리소스 문자열 ID입니다.  
  
 [in] `uiIconId`  
 보기 아이콘 id입니다.  
  
 [in] `iId`  
 뷰 id입니다.  
  
 [in] `lpszViewName`  
 뷰 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 마우스 동작을 지원 하기 위해 보기에 등록 해야는 `CMouseManager` 개체입니다. 파생 된 개체는 `CView` 마우스 관리자와 클래스를 등록할 수 있습니다. 문자열 및 보기와 연결 된 아이콘에 표시 됩니다는 **마우스** 탭은 **사용자 지정** 대화 상자.  
  
 것은 만들고와 같은 보기 Id를 유지 관리 하는 프로그래머의 책임 `iViewId` 및 `iId`합니다.  
  
 사용자 지정 마우스 동작을 제공 하는 방법에 대 한 자세한 내용은 참조 [키보드 및 마우스 사용자 지정](../../mfc/keyboard-and-mouse-customization.md)합니다.  
  
### <a name="example"></a>예  
 다음 예제에 대 한 포인터를 검색 하는 방법을 보여 줍니다는 `CMouseManager` 사용 하 여 개체는 `CWinAppEx::GetMouseManager` 메서드 및 `AddView` 에서 메서드는 `CMouseManager` 클래스입니다. 이 코드 조각은의 일부인는 [상태 컬렉션 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]  
  
##  <a name="getviewdblclickcommand"></a>CMouseManager::GetViewDblClickCommand  
 사용자 제공된 뷰 안에서 두 번 클릭할 때 실행 되는 명령을 반환 합니다.  
  
```  
UINT GetViewDblClickCommand(int iId) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iId`  
 보기 id입니다.  
  
### <a name="return-value"></a>반환 값  
 명령 식별자; 명령과 연결 된 경우 그렇지 않으면 0입니다.  
  
##  <a name="getviewiconid"></a>CMouseManager::GetViewIconId  
 Id가 보기 ID와 연결 된 아이콘을 검색 합니다.  
  
```  
UINT GetViewIconId(int iViewId) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iViewId`  
 보기 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 아이콘 리소스 식별자 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 뷰를 사용 하 여 먼저 등록 되지 않은 경우이 메서드를 사용할 [CMouseManager::AddView](#addview)합니다.  
  
##  <a name="getviewidbyname"></a>CMouseManager::GetViewIdByName  
 뷰 이름에 연결 된 뷰 ID를 검색 합니다.  
  
```  
int GetViewIdByName(LPCTSTR lpszName) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszName`  
 뷰 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 보기 ID 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 등록 하는 뷰를 통해 검색 [CMouseManager::AddView](#addview)합니다.  
  
##  <a name="getviewnames"></a>CMouseManager::GetViewNames  
 모든 등록 된 뷰 이름의 목록을 검색합니다.  
  
```  
void GetViewNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `listOfNames`  
 에 대 한 참조 `CStringList` 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 매개 변수를 채웁니다 `listOfNames` 사용 하 여 등록 된 모든 보기의 이름으로 [CMouseManager::AddView](#addview)합니다.  
  
##  <a name="loadstate"></a>CMouseManager::LoadState  
 상태를 로드는 [CMouseManager 클래스](../../mfc/reference/cmousemanager-class.md) 레지스트리에서 합니다.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 레지스트리 키의 경로입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 레지스트리에서 로드 된 상태 정보에는 등록 된 뷰, 뷰 식별자 및 연결 된 명령을 포함 됩니다. 경우 매개 변수 `lpszProfileName` 은 `NULL`,이 함수를 로드는 `CMouseManager` 으로 지정 된 기본 레지스트리 위치에서 데이터는 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)합니다.  
  
 대부분의 경우가이 함수를 직접 호출할 필요가 없습니다. 작업 영역 초기화 프로세스의 일부로 호출 됩니다. 작업 영역 초기화 프로세스에 대 한 자세한 내용은 참조 [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate)합니다.  
  
##  <a name="savestate"></a>CMouseManager::SaveState  
 상태는 [CMouseManager 클래스](../../mfc/reference/cmousemanager-class.md) 레지스트리에 합니다.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 레지스트리 키의 경로입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 레지스트리에 기록 된 상태 정보에는 등록 된 모든 뷰, 뷰 식별자 및 연결 된 명령을 포함 됩니다. 경우 매개 변수 `lpszProfileName` 은 `NULL`,이 함수를 작성는 `CMouseManager` 데이터에 의해 제어 기본 레지스트리 위치에는 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)합니다.  
  
 대부분의 경우가이 함수를 직접 호출할 필요가 없습니다. 작업 영역 serialization 프로세스의 일부로 호출 됩니다. 작업 영역 serialization 프로세스에 대 한 자세한 내용은 참조 [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate)합니다.  
  
##  <a name="setcommandfordblclk"></a>CMouseManager::SetCommandForDblClk  
 사용자 지정 명령을 마우스 관리자로 처음 등록 될 하는 보기에 연결 합니다.  
  
```  
void SetCommandForDblClk(
    int iViewId,  
    UINT uiCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iViewId`  
 뷰 식별자입니다.  
  
 [in] `uiCmd`  
 명령 식별자입니다.  
  
### <a name="remarks"></a>설명  
 사용자 지정 명령을 뷰를 연결 하려면 먼저 등록 해야 보기를 사용 하 여 [CMouseManager::AddView](#addview)합니다. `AddView` 메서드에 필요한 입력된 매개 변수로 뷰 식별자입니다. 호출할 수는 보기를 등록 하 고 나면 `CMouseManager::SetCommandForDblClk` 동일한 보기 식별자 입력 매개 변수를 제공 하는 `AddView`합니다. 그 후 사용자가 등록 된 보기에서 마우스를 응용 프로그램은 명령을 실행 하 여 표시 된 `uiCmd.` 마우스 사용자 지정 동작을 지원 하도록 해야 합니다 마우스 관리자에 등록 하는 보기를 사용자 지정할 수 있습니다. 사용자 지정 마우스 동작에 대 한 자세한 내용은 참조 [키보드 및 마우스 사용자 지정]--brokenlink--(... / 마우스 및 키보드 customization.md).  
  
 경우 `uiCmd` 설정 된 0으로의 지정 된 보기를 더 이상 명령과 연결 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)   
 [키보드 및 마우스 사용자 지정](../../mfc/keyboard-and-mouse-customization.md)



