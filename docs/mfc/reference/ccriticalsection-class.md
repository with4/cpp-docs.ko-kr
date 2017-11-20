---
title: "아니오 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
dev_langs: C++
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 351541763039abb4095785d562ee9ab22b30b74a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ccriticalsection-class"></a>아니오 클래스
"임계 섹션" 나타냅니다-코드 섹션 또는 리소스에 액세스 하려면 한 번에 하나의 스레드를 허용 하는 동기화 개체입니다.  
  
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
|[CCriticalSection::Lock](#lock)|에 대 한 액세스를 확보 하기 위해 사용할는 `CCriticalSection` 개체입니다.|  
|[CCriticalSection::Unlock](#unlock)|`CCriticalSection` 개체를 해제합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|내부에 대 한 포인터를 검색 **CRITICAL_SECTION** 개체입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CCriticalSection::m_sect](#m_sect)|A **CRITICAL_SECTION** 개체입니다.|  
  
## <a name="remarks"></a>설명  
 임계 영역은 데이터 또는 다른 제어 된 리소스가 수정으로 한 번에 하나의 스레드를 이동할 수 있는 경우에 유용 합니다. 예를 들어, 한 번에 한 스레드에서 허용 해야 하는 프로세스는 연결 된 목록의 노드를 추가 합니다. 사용 하 여 한 `CCriticalSection` 만 한 번에 한 스레드만 목록에 액세스할 수 있는 연결된 리스트를 제어 하는 개체입니다.  
  
> [!NOTE]
>  기능은 `CCriticalSection` 클래스 실제 Win32에서 제공 됩니다 **CRITICAL_SECTION** 개체입니다.  
  
 임계 영역 뮤텍스 대신 사용 됩니다 (참조 [CMutex](../../mfc/reference/cmutex-class.md)) 속도가 중요 한 시점과 프로세스 경계를 넘어 리소스 사용 되지 것입니다.  
  
 사용 하는 방법은 두 가지가 `CCriticalSection` 개체: 독립 실행형 및 클래스에 포함 합니다.  
  
-   독립 실행형 메서드를 사용 하 여 독립 실행형 `CCriticalSection` 개체를 생성 하는 `CCriticalSection` 필요할 때 개체입니다. 생성자에서 성공적으로 반환 된 후 호출 하 여 개체를 잠글 명시적으로 [잠금](#lock)합니다. 호출 [잠금 해제](#unlock) 완료 되 면 임계 영역에 액세스 합니다. 자세한 내용은 소스 코드를 읽는 사람에 게 하는 동안이 메서드는 이전 및 이후 액세스 임계 영역 잠금을 해제 해야 하는 대로 오류를 발생 시키기 합니다.  
  
     사용 하는 것이 좋습니다 더 메서드가 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 클래스입니다. 또한 한 `Lock` 및 `Unlock` 수 있지만 메서드를 예외가 발생 하는 경우에 리소스를 잠금 해제에 대해 걱정할 필요가 없습니다.  
  
-   메서드를 추가 하 여 다중 스레드를 가진 클래스를 공유할 수도 있습니다를 포함 한 `CCriticalSection`-형식 데이터 멤버는 클래스와 데이터 멤버 필요할 때 잠금.  
  
 사용 하 여 대 한 자세한 내용은 `CCriticalSection` 개체, 문서를 참조 하십시오. [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmt.h  
  
##  <a name="ccriticalsection"></a>CCriticalSection::CCriticalSection  
 `CCriticalSection` 개체를 생성합니다.  
  
```  
CCriticalSection();
```  
  
### <a name="remarks"></a>설명  
 에 액세스 하거나 해제 하려면는 `CCriticalSection` 개체를 만들기는 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 개체와 호출 해당 [잠금](../../mfc/reference/csinglelock-class.md#lock) 및 [잠금 해제](../../mfc/reference/csinglelock-class.md#unlock) 멤버 함수입니다. 경우는 `CCriticalSection` 호출, 개체가 독립 실행형 사용 되는 [잠금 해제](#unlock) 멤버 함수를 해제 합니다.  
  
 메모리 예외가 필요한 시스템 메모리를 할당 하는 생성자가 실패 하는 경우 (형식의 [CMemoryException](../../mfc/reference/cmemoryexception-class.md))이 자동으로 throw 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CCriticalSection::Lock](#lock)합니다.  
  
##  <a name="lock"></a>CCriticalSection::Lock  
 임계 영역 개체에 대 한 액세스 권한을 얻으려고이 멤버 함수를 호출 합니다.  
  
```  
BOOL Lock();  
BOOL Lock(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwTimeout`  
 `Lock`이 매개 변수 값을 무시합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 `Lock`임계 영역 개체의 신호를 보낼 때까지 반환 되지 것입니다 하는 차단 호출 (사용 가능).  
  
 대기 시간된을 필요한 경우 사용할 수 있습니다는 [CMutex](../../mfc/reference/cmutex-class.md) 개체가 아니라는 `CCriticalSection` 개체입니다.  
  
 경우 `Lock` 메모리 예외가 필요한 시스템 메모리 할당에 실패 (형식의 [CMemoryException](../../mfc/reference/cmemoryexception-class.md))이 자동으로 throw 됩니다.  
  
### <a name="example"></a>예제  
 이 예제에서는 공유 리소스에 대 한 액세스를 제어 하 여 중첩 된 임계 영역 방법을 보여 줍니다 (정적 `_strShared` 개체) 사용 하 여 공유 `CCriticalSection` 개체입니다. `SomeMethod` 함수 안전한 방법으로 공유 리소스를 업데이트 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]  
  
##  <a name="m_sect"></a>CCriticalSection::m_sect  
 전체에서 사용 되는 임계 영역 개체를 포함 `CCriticalSection` 메서드.  
  
```  
CRITICAL_SECTION m_sect;  
```  
  
##  <a name="operator_critical_section_star"></a>CCriticalSection::operator CRITICAL_SECTION *  
 검색 한 **CRITICAL_SECTION** 개체입니다.  
  
```  
operator CRITICAL_SECTION*();
```   
  
### <a name="remarks"></a>설명  
 내부에 대 한 포인터를 검색 하려면이 함수 호출 **CRITICAL_SECTION** 개체입니다.  
  
##  <a name="unlock"></a>CCriticalSection::Unlock  
 릴리스는 `CCriticalSection` 다른 스레드에서 사용 하기 위한 개체입니다.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `CCriticalSection` 스레드에서 개체를 소유 및 릴리스가 성공 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 경우는 `CCriticalSection` 독립 실행형을 사용 하 고 `Unlock` 임계 영역에 의해 제어 되는 리소스의 사용을 완료 한 후 바로 호출 해야 합니다. 경우는 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 개체 사용 중인 `CCriticalSection::Unlock` 잠금 개체에서 호출 되며 `Unlock` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CCriticalSection::Lock](#lock)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMutex 클래스](../../mfc/reference/cmutex-class.md)
