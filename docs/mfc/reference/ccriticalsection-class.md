---
title: "아니오 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, critical section
- CCriticalSection class
- critical sections
- synchronization classes, CCriticalSection class
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
caps.latest.revision: 21
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
ms.openlocfilehash: 25d4b124d089441503e9cb457e648695fc54660d
ms.lasthandoff: 02/24/2017

---
# <a name="ccriticalsection-class"></a>아니오 클래스
"임계 섹션" 나타냅니다-코드 섹션 또는 리소스에 액세스 하는 한 번에 하나의 스레드를 허용 하는 동기화 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CCriticalSection::CCriticalSection](#ccriticalsection)|`CCriticalSection` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CCriticalSection::Lock](#lock)|에 대 한 액세스 권한을 얻기 위해 사용 된 `CCriticalSection` 개체입니다.|  
|[CCriticalSection::Unlock](#unlock)|`CCriticalSection` 개체를 해제합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|내부 포인터를 검색 **CRITICAL_SECTION** 개체입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CCriticalSection::m_sect](#m_sect)|A **CRITICAL_SECTION** 개체입니다.|  
  
## <a name="remarks"></a>주의  
 임계 섹션은 데이터 나 일부 다른 제어 된 리소스를 수정으로 한 번에 하나의 스레드를 이동할 수 있는 경우에 유용 합니다. 예를 들어, 한 번에 한 스레드에서 허용 해야 하는 프로세스는 연결 된 목록의 노드를 추가 합니다. 사용 하 여 한 `CCriticalSection` 만 한 번에 하나의 스레드만 목록에 액세스할 수 있는 연결된 리스트를 제어 하는 개체입니다.  
  
> [!NOTE]
>  기능에서 `CCriticalSection` 클래스는 실제 Win32 제공한 **CRITICAL_SECTION** 개체입니다.  
  
 임계 영역 뮤텍스 대신 사용 됩니다 (참조 [CMutex](../../mfc/reference/cmutex-class.md)) 속도가 매우 중요 시점과 리소스 프로세스 경계를 넘어 사용 되지 것입니다.  
  
 사용 하기 위한 다음 두 가지가 있습니다는 `CCriticalSection` 개체: 독립 실행형 및 클래스에 포함 합니다.  
  
-   독립 실행형을 사용 하 여 독립 실행형 메서드 `CCriticalSection` 개체를 생성 하는 `CCriticalSection` 필요할 때 개체입니다. 생성자에서 성공적으로 반환 된 후 명시적으로 호출 하 여 개체 잠금 [잠금](#lock)합니다. 호출 [잠금 해제](#unlock) 마친 중요 섹션에 액세스 합니다. 소스 코드를 읽는 사람에 게 명확 하 게 파악할 하는 동안이 메서드를 하기가 더 쉽습니다 오류 잠금 액세스 전후 중요 섹션을 해제 하는 사실을 유의 해야 합니다.  
  
     사용 하는 것이 더 좋습니다.이 메서드는 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 클래스입니다. 또한 한 `Lock` 및 `Unlock` 메서드, 중요 하지 않은 예외가 발생 하는 경우에 리소스를 잠금 해제 하는 방법에 대 한 합니다.  
  
-   추가 하 여 다중 스레드를 가진 클래스를 공유할 수도 있습니다 메서드를 포함 한 `CCriticalSection`-클래스와 잠금 필요할 때 데이터 멤버 형식 데이터 멤버.  
  
 사용 하 여 대 한 자세한 내용은 `CCriticalSection` 개체, 문서를 참조 하십시오. [다중 스레딩: 동기화 클래스를 사용 하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmt.h  
  
##  <a name="a-nameccriticalsectiona--ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a>CCriticalSection::CCriticalSection  
 `CCriticalSection` 개체를 생성합니다.  
  
```  
CCriticalSection();
```  
  
### <a name="remarks"></a>주의  
 에 액세스 하거나 해제 하려면는 `CCriticalSection` 개체를 만들기는 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 개체와 호출 해당 [잠금](../../mfc/reference/csinglelock-class.md#lock) 및 [잠금 해제](../../mfc/reference/csinglelock-class.md#unlock) 멤버 함수입니다. 하는 경우는 `CCriticalSection` 개체를 독립 실행형으로 사용 되는 호출 하 고, 해당 [잠금 해제](#unlock) 멤버 함수를 해제 합니다.  
  
 생성자가 필요한 시스템 메모리를 메모리 예외를 할당에 실패 하는 경우 (형식의 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) 자동으로 throw 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CCriticalSection::Lock](#lock)합니다.  
  
##  <a name="a-namelocka--ccriticalsectionlock"></a><a name="lock"></a>CCriticalSection::Lock  
 임계 영역 개체에 액세스 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL Lock();  
BOOL Lock(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwTimeout`  
 `Lock`이 매개 변수 값을 무시합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 `Lock`임계 영역 개체에 신호가 전달 될 때까지 반환 하지 것입니다 하는 차단 호출 (사용 가능).  
  
 사용할 수 있습니다 대기 시간이 필요한 경우는 [CMutex](../../mfc/reference/cmutex-class.md) 개체가 아니라는 `CCriticalSection` 개체입니다.  
  
 경우 `Lock` 메모리 예외가 필요한 시스템 메모리 할당에 실패 (형식의 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) 자동으로 throw 됩니다.  
  
### <a name="example"></a>예제  
 이 예제에서는 공유 리소스에 대 한 액세스를 제어 하 여 중첩된 중요 섹션을 보여 줍니다 (정적 `_strShared` 개체) 공유를 사용 하 여 `CCriticalSection` 개체입니다. `SomeMethod` 함수에서 안전한 방식으로 공유 리소스를 업데이트 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_Utilities #&11;](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]  
  
##  <a name="a-namemsecta--ccriticalsectionmsect"></a><a name="m_sect"></a>CCriticalSection::m_sect  
 모두에서 사용 되는 임계 영역 개체를 포함 `CCriticalSection` 메서드.  
  
```  
CRITICAL_SECTION m_sect;  
```  
  
##  <a name="a-nameoperatorcriticalsectionstara--ccriticalsectionoperator-criticalsection"></a><a name="operator_critical_section_star"></a>CCriticalSection::operator CRITICAL_SECTION *  
 검색 한 **CRITICAL_SECTION** 개체입니다.  
  
```  
operator CRITICAL_SECTION*();
```   
  
### <a name="remarks"></a>주의  
 내부에 대 한 포인터를 검색 하려면이 함수를 호출 **CRITICAL_SECTION** 개체입니다.  
  
##  <a name="a-nameunlocka--ccriticalsectionunlock"></a><a name="unlock"></a>CCriticalSection::Unlock  
 릴리스는 `CCriticalSection` 다른 스레드에서 사용 하기 위한 개체입니다.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값은 `CCriticalSection` 스레드가 개체를 소유 하 고 릴리스가 성공 하 고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 하는 경우는 `CCriticalSection` 사용 되는 독립 실행형, `Unlock` 중요 섹션에 의해 제어 되는 리소스의 사용을 완료 한 후 바로 호출 해야 합니다. 하는 경우는 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 사용 되는 개체 `CCriticalSection::Unlock` 잠금 개체에서 호출 되며 `Unlock` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CCriticalSection::Lock](#lock)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMutex 클래스](../../mfc/reference/cmutex-class.md)

