---
title: "CMultiLock 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CMultiLock class
- synchronization objects, access control
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
caps.latest.revision: 20
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
ms.openlocfilehash: a58d59d8e4d7a1c542dee80295dd8eef6c8be338
ms.lasthandoff: 02/24/2017

---
# <a name="cmultilock-class"></a>CMultiLock 클래스
다중 스레드 프로그램에 대한 액세스를 제어할 때 사용하는 액세스 제어 메커니즘을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMultiLock  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMultiLock::CMultiLock](#cmultilock)|`CMultiLock` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMultiLock::IsLocked](#islocked)|배열에 있는 특정 동기화 개체가 잠겨 있는지 확인 합니다.|  
|[CMultiLock::Lock](#lock)|동기화 개체의 배열에 대 한 대기 합니다.|  
|[CMultiLock::Unlock](#unlock)|소유 동기화 개체를 해제합니다.|  
  
## <a name="remarks"></a>주의  
 `CMultiLock`기본 클래스는 없습니다.  
  
 동기화 클래스를 사용 하 여 [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), 및 [CEvent](../../mfc/reference/cevent-class.md)를 만들 수 있습니다는 **CMultiLock** 또는 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 개체를 대기 하 고 동기화 개체를 해제 합니다. 사용 하 여 **CMultiLock** 특정 시간에 사용할 수 있는 여러 개체에 있는 경우. 사용 하 여 `CSingleLock` 필요한 경우 한 번에 하나의 개체에서 대기 합니다.  
  
 사용 하는 **CMultiLock** 개체, 먼저 대기할 하고자 하는 동기화 개체의 배열을 만듭니다. 그런 다음 호출 하는 **CMultiLock** 제어 된 리소스의 클래스에서 멤버 함수 내부 개체의 생성자입니다. 그런 다음 호출에서 [잠금](#lock) 멤버 함수는 리소스를 사용할 수 있는지를 (신호). 하나를 나머지 멤버 함수를 계속 합니다. 사용할 수 없는 경우 지정된 된 양의 출시 될 리소스에 대 한 시간 기다리거나 오류를 반환 합니다. 리소스의 사용 하 여 완료 된 후 호출 하거나는 [잠금 해제](#unlock) 작동 하는 경우는 **CMultiLock** 개체를 다시 사용 하거나 허용 하는 **CMultiLock** 개체가 소멸 될 예정입니다.  
  
 **CMultiLock** 때 많은 수의 개체는 가장 유용한 `CEvent` 개체에 응답할 수 있습니다. 모든 포함 된 배열을 만듭니다는 `CEvent` 포인터 및 호출 `Lock`합니다. 이렇게 하면 스레드 이벤트 중 하나에 신호가 전달 될 때까지 기다려야 합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 **CMultiLock** 개체, 문서를 참조 하십시오. [다중 스레딩: 동기화 클래스를 사용 하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CMultiLock`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmt.h  
  
##  <a name="cmultilock"></a>CMultiLock::CMultiLock  
 생성 된 **CMultiLock** 개체입니다.  
  
```  
CMultiLock(
    CSyncObject* ppObjects [ ],  
    DWORD dwCount,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppObjects`  
 동기화 개체를 대기한 수에 대 한 포인터의 배열입니다. 안 **NULL**합니다.  
  
 `dwCount`  
 개체 수가 `ppObjects`합니다. 0보다 커야 합니다.  
  
 `bInitialLock`  
 제공 된 개체에 액세스 하려고 처음 것인지 지정 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 대기 수를 동기화 개체의 배열을 만든 후 호출 됩니다. 일반적으로 하나의 동기화 개체를 사용할 수 있을 때까지 대기 해야 하는 스레드 내에서 호출 됩니다.  
  
##  <a name="islocked"></a>CMultiLock::IsLocked  
 지정된 된 개체를 신호 없음으로 인지 여부를 확인 (사용할 수 없음).  
  
```  
BOOL IsLocked(DWORD dwItem);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwItem*  
 쿼리 중인 상태의 개체에 해당 하는 개체의 배열 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 개체가 잠겨 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="lock"></a>CMultiLock::Lock  
 하나 이상의 제공 된 동기화 개체에 의해 제어 되는 리소스에 액세스 하려면이 함수를 호출 하 여 **CMultiLock** 생성자입니다.  
  
```  
DWORD Lock(
    DWORD dwTimeOut = INFINITE,  
    BOOL bWaitForAll = TRUE,  
    DWORD dwWakeMask = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwTimeOut*  
 사용할 수 있는 동기화 개체에 대 한 대기 시간을 지정 합니다 (신호). 경우 **무한**, `Lock` 반환 하기 전에 개체에 신호가 전달 될 때까지 기다립니다.  
  
 `bWaitForAll`  
 대기한 모든 개체 반환 하기 전에 동시에 신호가 전달 해야 하는지 여부를 지정 합니다. 경우 **FALSE**, `Lock` 대기한 개체 중 하나에 신호가 전달 될 때 반환 됩니다.  
  
 `dwWakeMask`  
 허용 되는 대기를 중단 하는 다른 조건을 지정 합니다. 이 매개 변수에 대해 사용할 수 있는 옵션의 전체 목록은 참조 하십시오. [MsgWaitForMultipleObjects](http://msdn.microsoft.com/library/windows/desktop/ms684242) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 경우 `Lock` 실패 하면 반환-1입니다. 성공 하면 다음 값 중 하나가 반환 됩니다.  
  
-   사이의 **WAIT_OBJECT_0** 및 **WAIT_OBJECT_0** + (1-개체의 수)  
  
     경우 `bWaitForAll` 는 **TRUE**, 모든 개체 (사용 가능) 신호입니다. 경우 `bWaitForAll` 는 **FALSE**, 반환 값 – **WAIT_OBJECT_0** 는 신호를 받는 개체의 개체의 배열에서 인덱스 (사용 가능).  
  
- **WAIT_OBJECT_0** + (개체의 수)  
  
     에 지정 된 이벤트 `dwWakeMask` 스레드의 입력된 큐에서 사용할 수 있습니다.  
  
-   사이의 **WAIT_ABANDONED_0** 및 **WAIT_ABANDONED_0** + (1-개체의 수)  
  
     경우 `bWaitForAll` 는 **TRUE**, 신호는 모든 개체 및 개체 중 적어도 하나는 중단 된 뮤텍스 개체입니다. 경우 `bWaitForAll` 는 **FALSE**, 반환 값 – **WAIT_ABANDONED_0** 개체 대기를 만족 하는 중단 된 뮤텍스 개체의 배열에 있는 색인입니다.  
  
- **WAIT_TIMEOUT**  
  
     에 지정 된 시간 제한 간격 *dwTimeOut* 나중에 추가한 대기 하지 않고 만료 되었습니다.  
  
### <a name="remarks"></a>주의  
 경우 `bWaitForAll` 는 **TRUE**, `Lock` 동기화 개체를 모두 동시에 신호가 전달 되는 즉시 성공적으로 반환 합니다. 경우 `bWaitForAll` 는 **FALSE**, `Lock` 하나 이상의 동기화 개체가 신호를 받게 되는 즉시 반환 됩니다.  
  
 경우 `Lock` 에 지정 된 시간 (밀리초)의 개수 보다 더 기다리는 즉시 반환할 수 없는 *dwTimeOut* 반환 하기 전에 매개 변수입니다. 경우 *dwTimeOut* 는 **무한**, `Lock` 개체에 대 한 액세스는 또는 구성 요소에 지정 된 조건이 될 때까지 반환 하지 것입니다 `dwWakeMask` 충족 합니다. 그렇지 않은 경우, `Lock` 된 동기화 개체를 획득할 수를 반환 합니다 성공적으로; 그렇지 않으면 오류를 반환 합니다.  
  
##  <a name="unlock"></a>CMultiLock::Unlock  
 가 소유 하는 동기화 개체를 해제 `CMultiLock`합니다.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lCount`  
 해제 하려면 참조 수를 계산 합니다. 0보다 커야 합니다. 최대값을 초과 하는 개체의 수로 인해 지정 된 크기, 수는 변경 되지 않습니다 고 함수가 반환 **FALSE**합니다.  
  
 `lPrevCount`  
 동기화 개체에 대 한 이전 카운트를 수신 하는 변수를 가리킵니다. 경우 **NULL**, 이전 개수가 반환 되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하 `CMultiLock`의 소멸자입니다.  
  
 첫 번째 형태 `Unlock` 에서 관리 하는 동기화 개체의 잠금을 해제 하려고 `CMultiLock`합니다. 두 번째 형태 `Unlock` 잠금을 해제 하려고 시도 `CSemaphore` 가 소유한 개체 `CMultiLock`합니다. 경우 `CMultiLock` 소유 하지 않는 잠긴 `CSemaphore` 개체를 반환 하 고 **FALSE**고, 그렇지 않으면 반환 **TRUE**합니다. `lCount`및 `lpPrevCount` 동일의 매개 변수와 [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)합니다. 두 번째 형태 `Unlock` 거의 multilock 상황에 적용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




