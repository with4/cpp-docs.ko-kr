---
title: CJumpList 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CJumpList
- AFXADV/CJumpList
- AFXADV/CJumpList::CJumpList
- AFXADV/CJumpList::AbortList
- AFXADV/CJumpList::AddDestination
- AFXADV/CJumpList::AddKnownCategory
- AFXADV/CJumpList::AddTask
- AFXADV/CJumpList::AddTasks
- AFXADV/CJumpList::AddTaskSeparator
- AFXADV/CJumpList::ClearAll
- AFXADV/CJumpList::ClearAllDestinations
- AFXADV/CJumpList::CommitList
- AFXADV/CJumpList::GetDestinationList
- AFXADV/CJumpList::GetMaxSlots
- AFXADV/CJumpList::GetRemovedItems
- AFXADV/CJumpList::InitializeList
- AFXADV/CJumpList::SetAppID
dev_langs:
- C++
helpviewer_keywords:
- CJumpList [MFC], CJumpList
- CJumpList [MFC], AbortList
- CJumpList [MFC], AddDestination
- CJumpList [MFC], AddKnownCategory
- CJumpList [MFC], AddTask
- CJumpList [MFC], AddTasks
- CJumpList [MFC], AddTaskSeparator
- CJumpList [MFC], ClearAll
- CJumpList [MFC], ClearAllDestinations
- CJumpList [MFC], CommitList
- CJumpList [MFC], GetDestinationList
- CJumpList [MFC], GetMaxSlots
- CJumpList [MFC], GetRemovedItems
- CJumpList [MFC], InitializeList
- CJumpList [MFC], SetAppID
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d22fa264f48d3c5b1b6b88db338bc3be45c3f398
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369052"
---
# <a name="cjumplist-class"></a>CJumpList 클래스
A `CJumpList` 클릭할 작업 표시줄에서 아이콘에서 마우스 오른쪽 단추로 클릭할 때 표시 되는 바로 가기 목록입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CJumpList;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CJumpList::CJumpList](#cjumplist)|`CJumpList` 개체를 생성합니다.|  
|[CJumpList:: ~ CJumpList](#cjumplist__~cjumplist)|`CJumpList` 개체를 제거합니다.|  
  
|이름|설명|  
|----------|-----------------|  
|[CJumpList::AbortList](#abortlist)|목록 작성 트랜잭션을 커밋하지 않고 중단 합니다.|  
|[CJumpList::AddDestination](#adddestination)|오버로드됨. 대상 목록에 추가합니다.|  
|[CJumpList::AddKnownCategory](#addknowncategory)|알려진 범주 목록에 추가 합니다.|  
|[CJumpList::AddTask](#addtask)|오버로드됨. 정식 작업 범주에 항목을 추가합니다.|  
|[CJumpList::AddTasks](#addtasks)|정식 작업 범주에 항목을 추가합니다.|  
|[CJumpList::AddTaskSeparator](#addtaskseparator)|작업 사이 구분 기호를 추가합니다.|  
|[CJumpList::ClearAll](#clearall)|모든 작업 및 대상의 현재 인스턴스에 추가 된 제거 `CJumpList` 지금까지 합니다.|  
|[CJumpList::ClearAllDestinations](#clearalldestinations)|현재 인스턴스에 추가 된 모든 대상을 제거 `CJumpList` 지금까지 합니다.|  
|[CJumpList::CommitList](#commitlist)|목록 건물에서 트랜잭션을 종료 하 고 연결 된 저장소 (이 경우 레지스트리.)에 보고 된 목록을 커밋합니다.|  
|[CJumpList::GetDestinationList](#getdestinationlist)|대상 목록에 대 한 인터페이스 포인터를 검색합니다.|  
|[CJumpList::GetMaxSlots](#getmaxslots)|호출 응용 프로그램의 대상 메뉴에 표시할 수 있는 범주 헤더를 포함 하는 항목의 최대 수를 검색 합니다.|  
|[CJumpList::GetRemovedItems](#getremoveditems)|대상을 제거 하는 나타내는 항목의 배열을 반환 합니다.|  
|[CJumpList::InitializeList](#initializelist)|목록 작성 트랜잭션을 시작합니다.|  
|[CJumpList::SetAppID](#setappid)|빌드되는 목록에 대 한 응용 프로그램 사용자 모델 ID를 설정 합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxadv.h  
  
##  <a name="_dtorcjumplist"></a>  CJumpList:: ~ CJumpList  
 `CJumpList` 개체를 제거합니다.  
  
```  
~CJumpList();
```  
  
##  <a name="abortlist"></a>  CJumpList::AbortList  
 목록 작성 트랜잭션을 커밋하지 않고 중단 합니다.  
  
```  
void AbortList();
```  
  
### <a name="remarks"></a>설명  
 소멸 것과 동일한 결과가이 메서드를 호출 `CJumpList` 호출 하지 않고 `CommitList`합니다.  
  
##  <a name="adddestination"></a>  CJumpList::AddDestination  
 대상 목록에 추가합니다.  
  
```  
BOOL AddDestination(
    LPCTSTR lpcszCategoryName,  
    LPCTSTR strDestinationPath);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellItem* pShellItem);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpcszCategoryName`  
 범주 이름을 지정합니다. 지정된 된 범주가 없는 경우 생성 됩니다.  
  
 `strDestinationPath`  
 대상 파일의 경로를 지정합니다.  
  
 `strCategoryName`  
 범주 이름을 지정합니다. 지정된 된 범주가 없는 경우 생성 됩니다.  
  
 `pShellItem`  
 추가 중인 대상 나타내는 셸 항목을 지정 합니다.  
  
 `pShellLink`  
 추가 중인 대상 나타내는 셸 링크를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
 인스턴스 `CJumpList` 내부적으로 추가 된 대상에 따라 누적 되 고 다음에 커밋된 `CommitList`합니다.  
  
##  <a name="addknowncategory"></a>  CJumpList::AddKnownCategory  
 알려진 범주 목록에 추가 합니다.  
  
```  
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```  
  
### <a name="parameters"></a>매개 변수  
 `category`  
 알려진된 범주 유형을 지정합니다. 일 수 있습니다 `KDC_RECENT`, 또는 `KDC_KNOWN`합니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
 범주를 활용 하는 모든 응용 프로그램에 대 한 자동으로 계산 됩니다 하는 빈도 및 최근 범주는 알려진 `SHAddToRecentDocs` (또는 직접 사용 하지는 셸 응용 프로그램의 일부 시나리오에서는 대신 하 여 호출 됩니다).  
  
##  <a name="addtask"></a>  CJumpList::AddTask  
 정식 작업 범주에 항목을 추가합니다.  
  
```  
BOOL AddTask(
    LPCTSTR strTargetExecutablePath,  
    LPCTSTR strCommandLineArgs,  
    LPCTSTR strTitle,  
    LPCTSTR strIconLocation,  
    int iIconIndex);  
  
BOOL AddTask(IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>매개 변수  
 `strTargetExecutablePath`  
 대상 작업 경로 지정합니다.  
  
 `strCommandLineArgs`  
 StrTargetExecutablePath로 지정 된 실행 파일의 명령줄 인수를 지정 합니다.  
  
 `strTitle`  
 대상 목록에 표시 되는 작업 이름입니다.  
  
 `strIconLocation`  
 제목과 함께 대상 목록에 표시 되는 아이콘의 위치입니다.  
  
 `iIconIndex`  
 아이콘 인덱스입니다.  
  
 `pShellLink`  
 추가할 작업을 나타내는 셸 링크입니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
 인스턴스 `CJumpList` 지정 된 작업을 누적 하는 동안 대상 목록에 추가 및 `CommitList`합니다. 작업 항목은 응용 프로그램의 대상 메뉴 맨 아래에 범주에 표시 됩니다. 이 범주의 UI에 채워진 후 다른 모든 범주 보다 우선 합니다.  
  
##  <a name="addtasks"></a>  CJumpList::AddTasks  
 정식 작업 범주에 항목을 추가합니다.  
  
```  
BOOL AddTasks(IObjectArray* pObjectCollection);
```  
  
### <a name="parameters"></a>매개 변수  
 `pObjectCollection`  
 추가할 작업의 컬렉션입니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
 CJumpList의 인스턴스를 지정 된 작업을 누적 하 하는 동안 대상 목록에 추가 `CommitList`합니다. 작업 항목은 응용 프로그램의 대상 메뉴 맨 아래에 범주에 표시 됩니다. 이 범주의 UI에 채워진 후 다른 모든 범주 보다 우선 합니다.  
  
##  <a name="addtaskseparator"></a>  CJumpList::AddTaskSeparator  
 작업 사이 구분 기호를 추가합니다.  
  
```  
BOOL AddTaskSeparator();
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 하지 않으면 0입니다.  
  
##  <a name="cjumplist"></a>  CJumpList::CJumpList  
 `CJumpList` 개체를 생성합니다.  
  
```  
CJumpList(BOOL bAutoCommit = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bAutoCommit`  
 이 매개 변수가 FALSE 인 경우 소멸자의 목록은 자동으로 커밋되지 않은 합니다.  
  
##  <a name="clearall"></a>  CJumpList::ClearAll  
 모든 작업 및 대상의 현재 인스턴스에 추가 된 제거 `CJumpList` 지금까지 합니다.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>설명  
 이 메서드를 지우고 모든 데이터와 내부 인터페이스를 해제 합니다.  
  
##  <a name="clearalldestinations"></a>  CJumpList::ClearAllDestinations  
 지금까지 CJumpList의 현재 인스턴스에 추가 된 모든 대상을 제거 합니다.  
  
```  
void ClearAllDestinations();
```  
  
### <a name="remarks"></a>설명  
 지금까지 대상 목록 작성은 현재 세션에 추가 되 고 다른 대상에 다시 추가 하는 모든 대상을 제거 하려면 필요한 경우이 함수를 호출 합니다. 경우 내부 `ICustomDestinationList` 되었습니다 초기화 것은 활성 상태로 남아 있습니다.  
  
##  <a name="commitlist"></a>  CJumpList::CommitList  
 목록 건물에서 트랜잭션을 종료 하 고 연결 된 저장소 (이 경우 레지스트리)에 보고 된 목록을 커밋합니다.  
  
```  
BOOL CommitList();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
 커밋은 원자성을 갖습니다. 커밋에 실패 하면 오류가 반환 됩니다.  때 `CommitList` 라고, 현재 제거 된 항목 목록이 정리 됩니다. 활성 목록 건물 트랜잭션이 보유 하지 않는 개체를 다시 설정이 메서드를 호출 합니다. 목록을 업데이트 하려면 `BeginList` 다시 호출 해야 합니다.  
  
##  <a name="getdestinationlist"></a>  CJumpList::GetDestinationList  
 대상 목록에 대 한 인터페이스 포인터를 검색합니다.  
  
```  
ICustomDestinationList* GetDestinationList();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
 점프 목록 초기화 되지 않은 또는 커밋 또는 중단을 하는 경우 반환 되는 값 됩니다 `NULL`합니다.  
  
##  <a name="getmaxslots"></a>  CJumpList::GetMaxSlots  
 호출 응용 프로그램의 대상 메뉴에 표시할 수 있는 범주 헤더를 포함 하는 항목의 최대 수를 검색 합니다.  
  
```  
UINT GetMaxSlots() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
 응용 프로그램에는 다양 한 항목 및이 값 만큼 결합 된 범주 머리글 보고할만 수 있습니다. 경우에 대 한 호출이 `AppendCategory`, `AppendKnownCategory`, 또는 `AddUserTasks` 이 수를 초과, 오류를 반환 합니다.  
  
##  <a name="getremoveditems"></a>  CJumpList::GetRemovedItems  
 대상을 제거 하는 나타내는 항목의 배열을 반환 합니다.  
  
```  
IObjectArray* GetRemovedItems();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
 점프 목록 초기화 하는 동안 제거 된 대상은 검색 됩니다. 새 대상 목록을 생성 하는 경우 응용 프로그램 제거 목록 열거자에서 반환한 모든 항목에 대 한 추적 데이터를 지우는 제거 대상 목록에서 먼저 처리 하지 않을입니다. 응용 프로그램에 대 한 현재 호출에 트랜잭션에서 방금 제거 된 항목을 제공 하려고 할 경우 `BeginList` 시작 다시 해당 항목을 추가 하는 메서드 호출은 실패 합니다, 응용 프로그램 제거 목록을 엔진은 유지 되도록 합니다.  
  
##  <a name="initializelist"></a>  CJumpList::InitializeList  
 목록 작성 트랜잭션을 시작합니다.  
  
```  
BOOL InitializeList();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
 에 대 한 포인터를 검색 하려는 경우가 아니면이 메서드를 명시적으로 호출할 필요가 없습니다 `ICustomDestinationList` 를 사용 하 여 `GetDestinationList`를 사용 하 여 사용 가능한 슬롯 수가 `GetMaxSlots`, 또는 사용 하 여 제거 된 항목의 목록 `GetRemovedItems`합니다.  
  
##  <a name="setappid"></a>  CJumpList::SetAppID  
 빌드되는 목록에 대 한 응용 프로그램 사용자 모델 ID를 설정 합니다.  
  
```  
void SetAppID(LPCTSTR strAppID);
```  
  
### <a name="parameters"></a>매개 변수  
 `strAppID`  
 응용 프로그램 사용자 모델 ID를 지정 하는 문자열  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
