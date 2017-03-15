---
title: "CMFCTasksPaneTask 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTask
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTask class
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
caps.latest.revision: 27
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
ms.openlocfilehash: 20713b45c4b6aadc5cdfeaadb6ed269aaf7b337f
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask 클래스
`CMFCTasksPaneTask` 클래스는 작업 창 컨트롤에 대 한 작업을 나타내는 도우미 클래스 ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)). 작업 개체의 작업 그룹에서 항목을 나타냅니다 ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). 각 작업은 사용자가 작업을 클릭할 때 프레임워크가 실행하는 명령과 작업 이름의 왼쪽에 나타내는 아이콘을 포함할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|만들고 초기화는 `CMFCTasksPaneTask` 개체입니다.|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|현재 작업에 대 한 내게 필요한 옵션 데이터를 결정합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|작업 창이 자동으로 소멸 되 고 있는지 여부를 결정 합니다.|  
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|프레임 워크에서 굵은 텍스트로 작업 레이블 그릴지 여부를 결정 합니다.|  
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|프레임 워크를 태스크와 연결 하는 사용자 정의 데이터를 포함 합니다. 작업이 연결 된 데이터가 있으면&0;으로 설정 합니다.|  
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|작업 창에 대 한 핸들입니다.|  
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|프레임 워크 작업 옆에 표시 되는 이미지의 이미지 목록 인덱스입니다.|  
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|작업 창의 높이입니다. 작업에 작업 창이 있는 경우이 값은&0;입니다.|  
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|에 대 한 포인터는 `CMFCTasksPaneTaskGroup` 이 작업에 속하는 합니다.|  
|[CMFCTasksPaneTask::m_rect](#m_rect)|작업의 경계 사각형을 지정합니다.|  
|[CMFCTasksPaneTask::m_strName](#m_strname)|작업의 이름입니다.|  
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|작업을 마우스 오른쪽 단추로 클릭할 때 프레임 워크가 실행 되는 명령의 명령 ID를 지정 합니다. 이 값이 유효한 명령 ID가 아닐 경우 작업은 간단한 레이블로로 처리 됩니다.|  
  
## <a name="remarks"></a>주의  
 다음 그림에는 세 가지 작업을 포함 하는 작업 그룹을 보여 줍니다.  
  
 ![작업 그룹, 확장](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")  
  
> [!NOTE]
>  작업에 유효한 명령 ID를 찾을 수 없는 경우 간단한 레이블로 처리 됩니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxTasksPane.h  
  
##  <a name="a-namecmfctaskspanetaska--cmfctaskspanetaskcmfctaskspanetask"></a><a name="cmfctaskspanetask"></a>CMFCTasksPaneTask::CMFCTasksPaneTask  
 만들고 초기화는 `CMFCTasksPaneTask` 개체입니다.  
  
```  
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,  
    LPCTSTR lpszName,  
    int nIcon,  
    UINT uiCommandID,  
    DWORD dwUserData = 0,  
    HWND hwndTask = NULL,  
    BOOL bAutoDestroyWindow = FALSE,  
    int nWindowHeight = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `pGroup`  
 지정 된 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) 작업 속한 합니다.  
  
 `lpszName`  
 작업의 이름을 지정합니다.  
  
 `nIcon`  
 이미지 목록에서 작업의 이미지의 인덱스를 지정합니다.  
  
 `uiCommandID`  
 작업을 클릭할 때 실행 되는 명령의 명령 ID를 지정 합니다.  
  
 `dwUserData`  
 사용자 정의 데이터입니다.  
  
 `hwndTask`  
 작업 창에 대 한 핸들을 지정합니다.  
  
 `bAutoDestroyWindow`  
 경우 `TRUE`, 작업 창이 자동으로 소멸 됩니다.  
  
 `nWindowHeight`  
 작업 창의 높이 지정합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namembautodestroywindowa--cmfctaskspanetaskmbautodestroywindow"></a><a name="m_bautodestroywindow"></a>CMFCTasksPaneTask::m_bAutoDestroyWindow  
 작업 창이 자동으로 소멸 되 고 있는지 여부를 결정 합니다.  
  
```  
BOOL m_bAutoDestroyWindow;  
```  
  
### <a name="remarks"></a>주의  
 로 설정 `TRUE` 되도록 지정 하려면 작업 창 ( [CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)) 자동으로 고, 그렇지 않으면 제거 되어야 할지 `FALSE`합니다.  
  
##  <a name="a-namembisbolda--cmfctaskspanetaskmbisbold"></a><a name="m_bisbold"></a>CMFCTasksPaneTask::m_bIsBold  
 굵은 텍스트로 작업 레이블 그릴지 여부를 결정 합니다.  
  
```  
BOOL m_bIsBold;  
```  
  
### <a name="remarks"></a>주의  
 이 멤버를 설정 `TRUE` 작업 레이블에 대 한 굵은 텍스트로 표시 합니다.  
  
##  <a name="a-namemdwuserdataa--cmfctaskspanetaskmdwuserdata"></a><a name="m_dwuserdata"></a>CMFCTasksPaneTask::m_dwUserData  
 태스크와 연결 된 사용자 정의 데이터를 포함 합니다. 해당 작업과 관련 된 데이터가 없는 경우&0;으로 설정 합니다.  
  
```  
DWORD m_dwUserData;  
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namemhwndtaska--cmfctaskspanetaskmhwndtask"></a><a name="m_hwndtask"></a>CMFCTasksPaneTask::m_hwndTask  
 작업 창에 대 한 핸들입니다.  
  
```  
HWND m_hwndTask;  
```  
  
### <a name="remarks"></a>주의  
 작업 창에 추가 하려면 [CMFCTasksPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow)합니다.  
  
##  <a name="a-namemnicona--cmfctaskspanetaskmnicon"></a><a name="m_nicon"></a>CMFCTasksPaneTask::m_nIcon  
 지정된 된 작업 옆에 표시 되는 이미지를 식별 하는 이미지 목록에서 인덱스 위치입니다.  
  
```  
int m_nIcon;  
```  
  
### <a name="remarks"></a>주의  
 이미지 목록 설정 되어 [CMFCTasksPane::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist)합니다.  
  
 설정 `m_nIcon` 이미지 없는 작업을 표시 하려는 경우-1입니다.  
  
##  <a name="a-namemnwindowheighta--cmfctaskspanetaskmnwindowheight"></a><a name="m_nwindowheight"></a>CMFCTasksPaneTask::m_nWindowHeight  
 작업 창의 높이입니다. 작업에 작업 창이 있는 경우이 값은&0;입니다.  
  
```  
int m_nWindowHeight;  
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namempgroupa--cmfctaskspanetaskmpgroup"></a><a name="m_pgroup"></a>CMFCTasksPaneTask::m_pGroup  
 에 대 한 포인터는 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) 이 작업이 속한 합니다.  
  
```  
CMFCTasksPaneTaskGroup* m_pGroup;  
```  
  
### <a name="remarks"></a>주의  
 모든 작업에는 상위 그룹이 있어야 합니다. 호출 하 여 작업창으로 그룹을 추가한 [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)합니다.  
  
##  <a name="a-namemrecta--cmfctaskspanetaskmrect"></a><a name="m_rect"></a>CMFCTasksPaneTask::m_rect  
 작업의 경계 사각형을 지정합니다.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>주의  
 이 값은 작업을 그릴 때 프레임 워크에 의해 계산 됩니다.  
  
##  <a name="a-namemstrnamea--cmfctaskspanetaskmstrname"></a><a name="m_strname"></a>CMFCTasksPaneTask::m_strName  
 작업의 이름입니다.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namemuicommandida--cmfctaskspanetaskmuicommandid"></a><a name="m_uicommandid"></a>CMFCTasksPaneTask::m_uiCommandID  
 작업을 마우스 오른쪽 단추로 클릭할 때 실행 되는 명령의 명령 ID를 지정 합니다. 이 값이 유효한 명령 ID가 아닐 경우 작업은 간단한 레이블로로 처리 됩니다.  
  
```  
UINT m_uiCommandID;  
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namesetaccdataa--cmfctaskspanetasksetaccdata"></a><a name="setaccdata"></a>CMFCTasksPaneTask::SetACCData  
 현재 작업에 대 한 내게 필요한 옵션 데이터를 결정합니다.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParent`  
 현재 태스크의 부모 창을 나타냅니다.  
  
 [out] `data`  
 형식의 개체 `CAccessibilityData` 현재 태스크의 내게 필요한 옵션 데이터는 채워집니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`하는 경우는 `data` 매개 변수는 성공적으로 현재 작업의 내게 필요한 옵션 데이터로 채워진 하 고, 그렇지 않으면 `FALSE`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)

