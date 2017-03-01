---
title: "CMFCTasksPaneTaskGroup 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTaskGroup
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTaskGroup class
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
caps.latest.revision: 33
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
ms.openlocfilehash: 405a69a0c7d8c4179b36e1beec09fdfa7acd2d7b
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup 클래스
`CMFCTasksPaneTaskGroup` 클래스는 사용 되는 도우미 클래스는 [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) 제어 합니다. `CMFCTasksPaneTaskGroup` 형식의 개체는 *작업 그룹*을 나타냅니다. 작업 그룹은 축소 단추가 포함된 별도 상자에 프레임워크가 표시하는 항목 목록입니다. 상자는 선택적 캡션(그룹 이름)을 가질 수 있습니다. 그룹을 축소하면 작업 목록이 표시되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCTasksPaneTaskGroup : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|`CMFCTasksPaneTaskGroup` 개체를 생성합니다.|  
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|현재 작업 그룹에 대 한 내게 필요한 옵션 데이터를 결정합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|작업 그룹의 작업 창 컨트롤의 아래쪽으로 정렬 되는지 여부를 결정 합니다.|  
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|작업 그룹 축소 되는지 여부를 결정 합니다.|  
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|작업 그룹 인지 여부를 결정 *특별 합니다.* 프레임 워크는 다른 색으로 특별 한 캡션을 표시합니다.|  
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|작업의 내부 목록을 포함합니다.|  
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|그룹 제목의 경계 사각형을 지정합니다.|  
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|그룹의 경계 사각형을 지정합니다.|  
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|그룹의 이름을 지정합니다.|  
  
## <a name="remarks"></a>주의  
 다음 그림 확장 된 작업 그룹을 보여 줍니다.  
  
 ![작업 그룹, 확장](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")  
  
 다음 그림에는 축소 된 작업 그룹을 보여 줍니다.  
  
 ![축소 된 작업 그룹](../../mfc/reference/media/nexttaskgrpcollapse.png "nexttaskgrpcollapse")  
  
 다음 그림에는 캡션이 없는 작업 그룹을 보여 줍니다.  
  
 ![캡션이 없는 작업 그룹](../../mfc/reference/media/nexttaskgrpnocapt.png "nexttaskgrpnocapt")  
  
 다음 그림에서는 두 개의 작업 그룹을 보여 줍니다. 설정 하 여 첫 번째 작업 그룹으로 특수 표시는 `m_bIsSpecial` 플래그를 `TRUE`반면 두 번째 작업 그룹은 특별 합니다. 첫 번째 작업 그룹에 대 한 캡션을 두 번째 작업 그룹 보다 더 방식은 note:  
  
 ![특수 작업 그룹](../../mfc/reference/media/nexttaskgrpspecial.png "nexttaskgrpspecial")  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxTasksPane.h  
  
##  <a name="a-namecmfctaskspanetaskgroupa--cmfctaskspanetaskgroupcmfctaskspanetaskgroup"></a><a name="cmfctaskspanetaskgroup"></a>CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup  
 `CMFCTasksPaneTaskGroup` 개체를 생성합니다.  
  
```  
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,  
    BOOL bIsBottom,  
    BOOL bIsSpecial=FALSE,  
    BOOL bIsCollapsed=FALSE,  
    CMFCTasksPanePropertyPage* pPage=NULL,  
    HICON hIcon=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 그룹 제목을 그룹의 이름을 지정합니다.  
  
 `bIsBottom`  
 그룹 작업 창 컨트롤의 아래쪽으로 정렬 되는지 여부를 지정 합니다.  
  
 `bIsSpecial`  
 그룹으로 지정 된 여부 지정 *특수* 그룹 제목을 다른 색으로 채웁니다 여부에 따라서 합니다.  
  
 `bIsCollapsed`  
 그룹 축소 되는지 여부를 지정 합니다.  
  
 `pPage`  
 이 작업 그룹에 속하는 속성 페이지를 지정 합니다.  
  
 `hIcon`  
 그룹 제목을 표시 하는 아이콘을 지정 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namembisbottoma--cmfctaskspanetaskgroupmbisbottom"></a><a name="m_bisbottom"></a>CMFCTasksPaneTaskGroup::m_bIsBottom  
 작업 그룹의 작업 창 컨트롤의 아래쪽으로 정렬 되는지 여부를 결정 합니다.  
  
```  
BOOL m_bIsBottom;  
```  
  
### <a name="remarks"></a>주의  
 작업 창 컨트롤의 아래쪽에 하나의 그룹을 정렬할 수 있습니다. 이 작업 그룹은 마지막 추가 되어야 합니다. 자세한 내용은 참조 [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)합니다.  
  
##  <a name="a-namembiscollapseda--cmfctaskspanetaskgroupmbiscollapsed"></a><a name="m_biscollapsed"></a>CMFCTasksPaneTaskGroup::m_bIsCollapsed  
 작업 그룹 축소 되는지 여부를 결정 합니다.  
  
```  
BOOL m_bIsCollapsed;  
```  
  
### <a name="remarks"></a>주의  
 호출 하 여 작업 창에서 그룹을 축소 하는 기능을 사용 하지 않도록 설정 하거나 설정할 수 있습니다 [CMFCTasksPane::EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse)합니다.  
  
##  <a name="a-namembisspeciala--cmfctaskspanetaskgroupmbisspecial"></a><a name="m_bisspecial"></a>CMFCTasksPaneTaskGroup::m_bIsSpecial  
 작업 그룹 인지 여부를 결정 *특수* 특수 작업 그룹에 대 한 캡션을 다른 색으로 식별 해야 하는지 여부 및입니다.  
  
```  
BOOL m_bIsSpecial;  
```  
  
### <a name="remarks"></a>주의  
 응용 프로그램이 Windows XP 비주얼 테마를 사용 하는 경우 및 `m_bIsSpecial` 는 `FALSE`, 프레임 워크 호출 `DrawThemeBackground` 와 `EBP_NORMALGROUPBACKGROUND` 플래그입니다. 경우 `m_bIsSpecial` 는 `TRUE`, 프레임 워크 호출 `DrawThemeBackground` 와 `EBP_SPECIALGROUPBACKGROUND` 플래그입니다.  
  
##  <a name="a-namemlsttasksa--cmfctaskspanetaskgroupmlsttasks"></a><a name="m_lsttasks"></a>CMFCTasksPaneTaskGroup::m_lstTasks  
 작업의 내부 목록을 포함합니다.  
  
```  
CObList m_lstTasks;  
```  
  
### <a name="remarks"></a>주의  
 이 목록을 채우기 호출 [CMFCTasksPane::AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask)합니다.  
  
##  <a name="a-namemrecta--cmfctaskspanetaskgroupmrect"></a><a name="m_rect"></a>CMFCTasksPaneTaskGroup::m_rect  
 그룹 제목의 경계 사각형을 지정합니다.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>주의  
 이 값은 프레임 워크에 의해 자동으로 계산 됩니다.  
  
##  <a name="a-namemrectgroupa--cmfctaskspanetaskgroupmrectgroup"></a><a name="m_rectgroup"></a>CMFCTasksPaneTaskGroup::m_rectGroup  
 그룹의 경계 사각형을 지정합니다.  
  
```  
CRect m_rectGroup;  
```  
  
### <a name="remarks"></a>주의  
 이 값은 프레임 워크에 의해 자동으로 계산 됩니다.  
  
##  <a name="a-namemstrnamea--cmfctaskspanetaskgroupmstrname"></a><a name="m_strname"></a>CMFCTasksPaneTaskGroup::m_strName  
 그룹의 이름을 지정합니다.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>주의  
 이 값이 비어 있으면 그룹 제목을 표시 되지 않으며 그룹을 축소할 수 없습니다.  
  
##  <a name="a-namesetaccdataa--cmfctaskspanetaskgroupsetaccdata"></a><a name="setaccdata"></a>CMFCTasksPaneTaskGroup::SetACCData  
 현재 작업 그룹에 대 한 내게 필요한 옵션 데이터를 결정합니다.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParent`  
 현재 작업 그룹의 부모 창을 나타냅니다.  
  
 [out] `data`  
 형식의 개체 `CAccessibilityData` 현재 작업 그룹의 내게 필요한 옵션 데이터는 채워집니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`하는 경우는 `data` 매개 변수는 성공적으로 현재 작업 그룹의 내게 필요한 옵션 데이터로 채워진 하 고, 그렇지 않으면 `FALSE`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCTasksPane 클래스](../../mfc/reference/cmfctaskspane-class.md)   
 [CMFCTasksPaneTask 클래스](../../mfc/reference/cmfctaskspanetask-class.md)   
 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)

