---
title: "CMouseManager 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CMouseManager class
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: 26
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7ba50f976f6cf9d6b701e39304c50507cfa34cc5
ms.lasthandoff: 02/24/2017

---
# <a name="cmousemanager-class"></a>CMouseManager 클래스
사용자 특정와 다양 한 명령을 연결할 수 있도록 [CView](../../mfc/reference/cview-class.md) 사용자가 뷰 안에서 두 번 클릭할 때 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMouseManager : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMouseManager::AddView](#addview)|추가 `CView` 개체는 **사용자 지정** 대화 상자입니다. **사용자 지정** 대화 상자에서는 사용자를 두 번 클릭을 각 나열된 된 보기의 명령을 사용 하 여 연결 합니다.|  
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|제공 된 보기 내 번 클릭할 때 실행 되는 명령을 반환 합니다.|  
|[CMouseManager::GetViewIconId](#getviewiconid)|제공 된 보기 ID와 연결 된 아이콘을 반환 합니다.|  
|[CMouseManager::GetViewIdByName](#getviewidbyname)|제공 된 뷰 이름에 연결 된 뷰 ID를 반환 합니다.|  
|[CMouseManager::GetViewNames](#getviewnames)|모든 추가 된 뷰 이름의 목록을 검색합니다.|  
|[CMouseManager::LoadState](#loadstate)|로드 된 `CMouseManager` Windows 레지스트리에서 상태입니다.|  
|[CMouseManager::SaveState](#savestate)|기록 된 `CMouseManager` Windows 레지스트리에 상태입니다.|  
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|제공된 된 명령 및 제공 된 보기에 연결합니다.|  
  
## <a name="remarks"></a>주의  
 `CMouseManager` 클래스의 컬렉션을 유지 `CView` 개체입니다. 각 보기는 식별 이름으로 id입니다. 이러한 보기에 표시 되는 **사용자 지정** 대화 상자입니다. 사용자가 연결 된 모든 보기를 통해 명령을 변경할 수는 **사용자 지정** 대화 상자입니다. 사용자가 해당 보기에에서는 관련 된 명령이 실행 됩니다. 이 지원 하기 코딩 관점에서에서 처리 해야는 `WM_LBUTTONDBLCLK` 메시지 및 호출에서 [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) 함수에 대 한 코드에서 `CView` 개체...  
  
 만들어야 합니다를 `CMouseManager` 개체를 수동으로. 응용 프로그램의 프레임 워크에 의해 생성 됩니다. 사용자가 응용 프로그램을 종료할 때 자동으로 소멸도 됩니다. 응용 프로그램에 대 한 마우스 관리자에 대 한 포인터를 가져오려면, 호출 [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMouseManager`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmousemanager.h  
  
##  <a name="addview"></a>CMouseManager::AddView  
 등록 한 [CView](../../mfc/reference/cview-class.md) 개체는 [CMouseManager 클래스](../../mfc/reference/cmousemanager-class.md) 마우스 사용자 지정 동작을 지원 하도록 합니다.  
  
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
  
### <a name="remarks"></a>주의  
 사용자 지정 마우스 동작을 지원 하기 위해 보기에 등록 해야는 `CMouseManager` 개체입니다. 파생 된 모든 개체는 `CView` 마우스 관리자와 클래스를 등록할 수 있습니다. 문자열 및 보기와 연결 된 아이콘에 표시 됩니다는 **마우스** 탭은 **사용자 지정** 대화 상자입니다.  
  
 만들어 뷰 Id를 유지 관리와 같은 프로그래머의 책임 `iViewId` 및 `iId`합니다.  
  
 사용자 지정 마우스 동작을 제공 하는 방법에 대 한 자세한 내용은 참조 [키보드 및 마우스 사용자 지정](../../mfc/keyboard-and-mouse-customization.md)합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는에 대 한 포인터를 검색 하는 방법을 `CMouseManager` 사용 하 여 개체는 `CWinAppEx::GetMouseManager` 메서드 및 `AddView` 에서 메서드는 `CMouseManager` 클래스입니다. 이 코드 조각은의 일부인는 [상태 컬렉션 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_StateCollection #&4;](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]  
  
##  <a name="getviewdblclickcommand"></a>CMouseManager::GetViewDblClickCommand  
 제공 된 보기 내 번 클릭할 때 실행 되는 명령을 반환 합니다.  
  
```  
UINT GetViewDblClickCommand(int iId) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iId`  
 보기 id입니다.  
  
### <a name="return-value"></a>반환 값  
 Command;와 연결 된 경우에 명령 식별자 그렇지 않으면 0입니다.  
  
##  <a name="getviewiconid"></a>CMouseManager::GetViewIconId  
 뷰 ID와 연결 된 아이콘을 검색 합니다.  
  
```  
UINT GetViewIconId(int iViewId) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iViewId`  
 보기 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 아이콘 리소스 식별자 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 보기를 사용 하 여 먼저 등록 되지 않은 경우이 메서드를 사용할 [CMouseManager::AddView](#addview)합니다.  
  
##  <a name="getviewidbyname"></a>CMouseManager::GetViewIdByName  
 뷰 이름에 연결 된 뷰 ID를 검색 합니다.  
  
```  
int GetViewIdByName(LPCTSTR lpszName) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszName`  
 뷰 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우에 뷰 ID 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 등록 하는 뷰를 통해 검색 [CMouseManager::AddView](#addview)합니다.  
  
##  <a name="getviewnames"></a>CMouseManager::GetViewNames  
 모든 등록 된 뷰 이름 목록을 검색합니다.  
  
```  
void GetViewNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `listOfNames`  
 에 대 한 참조 `CStringList` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 매개 변수를 채웁니다 `listOfNames` 를 사용 하 여 등록 된 모든 보기의 이름으로 [CMouseManager::AddView](#addview)합니다.  
  
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
  
### <a name="remarks"></a>주의  
 레지스트리에서 로드 된 상태 정보에는 등록 된 뷰, 뷰 식별자 및 연결 된 명령을 포함 됩니다. 경우 매개 변수 `lpszProfileName` 는 `NULL`,이 함수를 로드는 `CMouseManager` 으로 지정 된 기본 레지스트리 위치에서 데이터는 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)합니다.  
  
 대부분의 경우가이 함수를 직접 호출할 필요가 없습니다. 작업 영역 초기화 프로세스의 일부로 호출 됩니다. 작업 영역 초기화 프로세스에 대 한 자세한 내용은 참조 [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate)합니다.  
  
##  <a name="savestate"></a>CMouseManager::SaveState  
 상태를 기록 된 [CMouseManager 클래스](../../mfc/reference/cmousemanager-class.md) 레지스트리에 있습니다.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 레지스트리 키의 경로입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 레지스트리에 기록 된 상태 정보에는 등록 된 모든 뷰, 뷰 식별자 및 연결 된 명령을 포함 됩니다. 경우 매개 변수 `lpszProfileName` 는 `NULL`,이 함수는 씁니다는 `CMouseManager` 에 의해 제어 기본 레지스트리 위치에 대 한 데이터는 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)합니다.  
  
 대부분의 경우가이 함수를 직접 호출할 필요가 없습니다. 작업 영역 serialization 프로세스의 일부로 호출 됩니다. 작업 영역 serialization 프로세스에 대 한 자세한 내용은 참조 [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate)합니다.  
  
##  <a name="setcommandfordblclk"></a>CMouseManager::SetCommandForDblClk  
 사용자 지정 명령을 마우스 관리자를 처음 등록 하는 보기에 연결 합니다.  
  
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
  
### <a name="remarks"></a>주의  
 사용자 지정 명령 보기를 연결 하려면 먼저 등록 해야 보기를 사용 하 여 [CMouseManager::AddView](#addview)합니다. `AddView` 메서드에 필요한 입력된 매개 변수로 뷰 식별자입니다. 호출할 수는 보기를 등록 하 고 나면 `CMouseManager::SetCommandForDblClk` 동일한 뷰 식별자 입력 매개 변수를 제공 하는 `AddView`합니다. 이후부터 등록 된 보기에서 마우스를 클릭할 때 응용 프로그램은 명령을 실행 하 여 표시 된 `uiCmd.` 마우스 사용자 지정 동작을 지원 하려면 또한 할 마우스 관리자에 등록 하는 보기를 사용자 지정 합니다. 사용자 지정 마우스 동작에 대 한 자세한 내용은 참조 [키보드 및 마우스 사용자 지정]--brokenlink--(... / 마우스 및 키보드 customization.md).  
  
 경우 `uiCmd` 설정 된 0으로 지정된 된 보기 더 이상 연결 되어 명령에 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)   
 [키보드 및 마우스 사용자 지정](../../mfc/keyboard-and-mouse-customization.md)




