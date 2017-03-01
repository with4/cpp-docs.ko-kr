---
title: "CEvent 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEvent
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, event
- synchronization classes, CEvent class
- CEvent class
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
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
ms.openlocfilehash: 9edadeec87cf04ae6166c173c65463d1509eb1d8
ms.lasthandoff: 02/24/2017

---
# <a name="cevent-class"></a>CEvent 클래스
한 스레드가 다른 이벤트가 발생 했음을 알릴 수 있도록 하는 동기화 개체인 이벤트를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CEvent : public CSyncObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CEvent::CEvent](#cevent)|`CEvent` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CEvent::PulseEvent](#pulseevent)|설정은 이벤트를 사용할 수 있는 (신호)를 대기 중인 스레드를 해제 하 고 이벤트 (신호)를 사용할 수 없도록 설정 합니다.|  
|[CEvent::ResetEvent](#resetevent)|이벤트 (신호)를 사용할 수 없도록 설정합니다.|  
|[CEvent::SetEvent](#setevent)|(신호)를 사용할 수 있는 이벤트를 설정 하 고 모든 대기 중인 스레드를 해제 합니다.|  
|[CEvent::Unlock](#unlock)|이벤트 개체를 해제합니다.|  
  
## <a name="remarks"></a>주의  
 이벤트는 스레드가 해당 작업을 수행 하는 시기를 알고 있어야 하는 경우에 유용 합니다. 예를 들어 새 데이터를 사용할 수는 데이터 보관 파일에 데이터를 복사 하는 스레드는 알림이 표시 해야 합니다. 사용 하 여 한 `CEvent` 새 데이터를 사용할 수 있는 경우 복사 스레드를 알리는 개체 스레드는 작업을 가능한 한 빨리 수행할 수 있습니다.  
  
 `CEvent`개체에는 두 가지 유형: 수동 및 자동입니다.  
  
 자동 `CEvent` 개체 신호 (사용할 수 없음) 상태에 하나 이상의 스레드가 해제 된 후 자동으로 반환 합니다. 기본적으로는 `CEvent` 전달 하지 않으면 개체는 자동 `TRUE` 에 대 한는 `bManualReset` 생성 되는 동안 매개 변수입니다.  
  
 수동 `CEvent` 으로 설정 된 상태에 유지 되는 개체 [SetEvent](#setevent) 또는 [ResetEvent](#resetevent) 다른 함수를 호출할 때까지 합니다. 수동 만들려면 `CEvent` 개체를 전달 하며, `TRUE` 에 대 한는 `bManualReset` 생성 되는 동안 매개 변수입니다.  
  
 사용 하는 `CEvent` 개체 생성는 `CEvent` 필요할 때 개체입니다. 이벤트를 대기 하 고 응용 프로그램은 처음에 소유 하 고 있음을 지정 하려는 이름을 지정 합니다. 그런 다음 생성자는 반환 될 때 이벤트를 액세스할 수 있습니다. 호출 [SetEvent](#setevent) 신호 (계산에 사용할 수 있는 경우)에 이벤트 개체와 다음 호출 [잠금 해제](#unlock) 후 제어 된 리소스에 액세스 합니다.  
  
 대체 방법을 사용 하 여 `CEvent` 개체 형식의 변수를 추가 하는 것 `CEvent` 를 제어 하려고 하는 클래스를 데이터 멤버로 합니다. 제어 되는 개체의 생성 하는 동안의 생성자를 호출는 `CEvent` 데이터 멤버 및 또한 이벤트가 처음 신호 여부 및 specifythe 유형의 이벤트 개체를 이벤트 (프로세스 경계를 넘어 사용 됨) 하는 경우의 이름 지정 하 고 모든 보안 특성 원하는 합니다.  
  
 에 의해 제어 되는 리소스에 액세스 하는 `CEvent` 이 방식으로 개체를 먼저 두 가지 형식의 변수를 만들고 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 또는 형식 [CMultiLock](../../mfc/reference/cmultilock-class.md) 리소스의 액세스 방법에 있습니다. 그런 다음 호출에서 `Lock` 잠금 개체의 메서드 (예를 들어 [CMultiLock::Lock](../../mfc/reference/cmultilock-class.md#lock)). 이 시점에서 스레드 중 하나 리소스, 리소스를 해제 하 고, 액세스 하거나 출시 될 리소스를 대기에 대 한 대기 시간 초과에 대 한 액세스를 얻을 수를 리소스에 액세스 하기에 실패 합니다. 어떤 경우 든 스레드로부터 안전한 방식으로 리소스에 액세스 합니다. 리소스를 해제 하려면 호출 `SetEvent` 이벤트 개체를 신호로 알리는을 사용 하 여는 `Unlock` 잠금 개체의 메서드 (예를 들어 [CMultiLock::Unlock](../../mfc/reference/cmultilock-class.md#unlock)), 또는 잠금 개체 범위를 벗어날 수 있습니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CEvent` 개체를 참고 하십시오 [다중 스레딩: 동기화 클래스를 사용 하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities #&45;](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]  
  
 [!code-cpp[NVC_MFC_Utilities #&46;](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CEvent`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmt.h  
  
##  <a name="a-nameceventa--ceventcevent"></a><a name="cevent"></a>CEvent::CEvent  
 명명 되거나 명명 되지 않은에서는 `CEvent` 개체입니다.  
  
```  
CEvent(
    BOOL bInitiallyOwn = FALSE,  
    BOOL bManualReset = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `bInitiallyOwn`  
 경우 **TRUE**에 대 한 스레드는 **CMultilock** 또는 `CSingleLock` 개체를 사용할 수 있습니다. 그렇지 않은 경우 리소스에 액세스 하려는 모든 스레드가 대기 해야 합니다.  
  
 *bManualReset*  
 경우 **TRUE**, 이벤트 개체는 수동 이벤트, 그렇지 않으면 이벤트 개체는 자동 이벤트를 지정 합니다.  
  
 `lpszName`  
 `CEvent` 개체의 이름입니다. 프로세스 경계를 넘어 개체를 사용할 예정 이면 제공 되어야 합니다. 이름이 일치 하는 기존 이벤트, 생성자 빌드하여 새 `CEvent` 해당 이름의 이벤트를 참조 하는 개체입니다. 이름이 일치가 이벤트가 아닌 기존 동기화 개체를 생성 하지 못합니다. 경우 **NULL**, 이름이 null이 됩니다.  
  
 `lpsaAttribute`  
 이벤트 개체에 대 한 보안 특성입니다. 에 대 한 전체 설명은이 구조를 참조 하십시오. [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 에 액세스 하거나 해제 하려면는 `CEvent` 개체를 만들기는 [CMultiLock](../../mfc/reference/cmultilock-class.md) 또는 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 개체와 호출 해당 [잠금](../../mfc/reference/csinglelock-class.md#lock) 및 [잠금 해제](../../mfc/reference/csinglelock-class.md#unlock) 멤버 함수입니다.  
  
 상태를 변경 하는 `CEvent` 개체가 신호를 (스레드를 하지 않은 기다려야) 호출 [SetEvent](#setevent) 또는 [PulseEvent](#pulseevent)합니다. 상태를 설정 하는 `CEvent` 개체를 신호 없음으로 (스레드가 기다려야), 호출 [ResetEvent](#resetevent)합니다.  
  
> [!IMPORTANT]
>  만든 후의 `CEvent` 개체를 사용 하 여 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 뮤텍스 존재 하지 않는 새로운 되도록 합니다. 뮤텍스가 예기치 않게 존재, 불량 프로세스 무단 점유 되 고 뮤텍스를 악의적으로 사용 하 여 시도 수를 나타낼 수 있습니다. 이 경우 권장 되는 보안에 민감한 절차를 처리 및 개체를 만들 오류가 발생 한 경우 처럼 계속입니다.  
  
##  <a name="a-namepulseeventa--ceventpulseevent"></a><a name="pulseevent"></a>CEvent::PulseEvent  
 (사용 가능)에서 신호를 이벤트의 상태를 설정, 모든 대기 중인 스레드를 해제 하 고이를 신호 없음으로 (사용할 수 없음)를 자동으로 다시 설정 합니다.  
  
```  
BOOL PulseEvent();
```  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이벤트 수동, 모든 대기 중인 스레드가 해제 되 면 이벤트가 신호 없음으로 설정 되 고 `PulseEvent` 를 반환 합니다. 이벤트 자동, 단일 스레드가 해제 되 면 이벤트가 신호 없음으로 설정 하 고 `PulseEvent` 를 반환 합니다.  
  
 대기 중인 스레드가 없는 경우 스레드가 즉시 해제할 수 `PulseEvent` 이벤트의 상태를 신호 없음으로 설정 하 고 반환 합니다.  
  
 `PulseEvent`기본 Win32를 사용 하 여 `PulseEvent` 함수는 커널 모드 비동기 프로시저 호출 하 여 대기 상태에서 일시적으로 제거할 수 있습니다. 따라서 `PulseEvent` 불안정 하 고 새 응용 프로그램으로 쓰일 수 없습니다. 자세한 내용은 참조는 [PulseEvent 함수](http://msdn.microsoft.com/library/windows/desktop/ms684914)합니다.  
  
##  <a name="a-namereseteventa--ceventresetevent"></a><a name="resetevent"></a>CEvent::ResetEvent  
 상태를 설정 이벤트를 신호 없음으로까지 여에 신호를 명시적으로 설정 된 [SetEvent](#setevent) 멤버 함수입니다.  
  
```  
BOOL ResetEvent();
```  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이렇게 하면 모든 스레드가 대기 하는이 이벤트에 액세스 하려는 됩니다.  
  
 이 멤버 함수는 자동 이벤트에 의해 사용 되지 않습니다.  
  
##  <a name="a-nameseteventa--ceventsetevent"></a><a name="setevent"></a>CEvent::SetEvent  
 모든 대기 중인 스레드를 해제 하는 상태를 신호 이벤트를 설정 합니다.  
  
```  
BOOL SetEvent();
```  
  
### <a name="return-value"></a>반환 값  
 함수가 성공한 경우 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이벤트 신호를 받은 될 때까지 유지 됩니다 이벤트 수동 이면 [ResetEvent](#resetevent) 호출 됩니다. 이 경우 둘 이상의 스레드를 릴리스할 수 있습니다. 이 이벤트는 자동이 단일 스레드가 해제 될 때까지 이벤트 신호를 받은 상태로 유지 됩니다. 그런 다음 시스템을 신호 없음으로 이벤트의 상태를 설정 합니다. 대기 중인 스레드가 없는 경우에 한 스레드가 해제 될 때까지 상태 신호를 받은 상태로 유지 됩니다.  
  
##  <a name="a-nameunlocka--ceventunlock"></a><a name="unlock"></a>CEvent::Unlock  
 이벤트 개체를 해제합니다.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>반환 값  
 이벤트 개체 및 이벤트 스레드가 소유 하는 경우 0이 아닌 값은 자동 이벤트; 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 현재 해당 잠금 개체를 다시 사용할 수 있으면를 완료 한 후 해제 하는 자동 이벤트를 소유한 스레드에 의해 호출 됩니다. 잠금 개체를 다시 사용 하지 않는 경우이 함수는 잠금 개체의 소멸자에 의해 호출 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)


