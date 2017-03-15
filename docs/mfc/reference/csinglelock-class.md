---
title: "경우 CSingleLock 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleLock
dev_langs:
- C++
helpviewer_keywords:
- CSingleLock class
- threading [MFC], access control
- synchronization objects, access control
- threading [MFC], synchronization
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
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
ms.openlocfilehash: b1efc2daf1c3714446223cc69f9cc2a6a3401173
ms.lasthandoff: 02/24/2017

---
# <a name="csinglelock-class"></a>경우 CSingleLock 클래스
다중 스레드 프로그램에서 한 리소스에 대한 액세스를 제어할 때 사용하는 액세스 제어 메커니즘을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSingleLock  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSingleLock::CSingleLock](#csinglelock)|`CSingleLock` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSingleLock::IsLocked](#islocked)|개체가 잠겨 있는지 확인 합니다.|  
|[CSingleLock::Lock](#lock)|동기화 개체를 대기합니다.|  
|[CSingleLock::Unlock](#unlock)|동기화 개체를 해제합니다.|  
  
## <a name="remarks"></a>주의  
 `CSingleLock`기본 클래스는 없습니다.  
  
 동기화 클래스를 사용 하려면 [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [아니오](../../mfc/reference/ccriticalsection-class.md), 및 [CEvent](../../mfc/reference/cevent-class.md)를 하나 만들어야 합니다를 `CSingleLock` 또는 [CMultiLock](../../mfc/reference/cmultilock-class.md) 개체를 대기 하 고 동기화 개체를 해제 합니다. 사용 하 여 `CSingleLock` 필요한 경우 한 번에 하나의 개체에서 대기 합니다. 사용 하 여 **CMultiLock** 특정 시간에 사용할 수 있는 여러 개체에 있는 경우.  
  
 사용 하는 `CSingleLock` 개체, 제어 된 리소스의 클래스에서 멤버 함수 내 해당 생성자를 호출 합니다. 그런 다음 호출에서 [IsLocked](#islocked) 멤버 함수는 리소스를 사용할 수 있는지를 합니다. 그럴 경우 멤버 함수의 나머지를 계속 합니다. 리소스를 사용할 수 없는 경우 지정된 된 양의 출시 될 리소스에 대 한 시간에 대 한 대기 또는 실패를 반환 합니다. 리소스 사용이 완료 된 후 호출 하거나는 [잠금 해제](#unlock) 작동 하는 경우는 `CSingleLock` 개체를 다시 사용 하거나 허용 하는 `CSingleLock` 개체 소멸 될 예정입니다.  
  
 `CSingleLock`개체에서 파생 된 개체의 존재를 필요 [CSyncObject](../../mfc/reference/csyncobject-class.md)합니다. 이 일반적으로 제어 된 리소스 클래스의 데이터 멤버입니다. 사용 하는 방법에 대 한 자세한 내용은 `CSingleLock` 개체, 문서를 참조 하십시오. [다중 스레딩: 동기화 클래스를 사용 하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CSingleLock`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmt.h  
  
##  <a name="a-namecsinglelocka--csinglelockcsinglelock"></a><a name="csinglelock"></a>CSingleLock::CSingleLock  
 `CSingleLock` 개체를 생성합니다.  
  
```  
explicit CSingleLock(
    CSyncObject* pObject,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pObject`  
 에 액세스할 수 있는 동기화 개체를 가리킵니다. 안 **NULL**합니다.  
  
 `bInitialLock`  
 제공된 된 개체에 액세스 하려고 처음 것인지 지정 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 일반적으로 제어 되는 리소스의 액세스 멤버 함수 내에서 호출 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities #&19;](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]  
  
##  <a name="a-nameislockeda--csinglelockislocked"></a><a name="islocked"></a>CSingleLock::IsLocked  
 개체 관련 된 결정의 `CSingleLock` 개체를 신호 없음으로 (사용할 수 없음).  
  
```  
BOOL IsLocked();
```  
  
### <a name="return-value"></a>반환 값  
 개체가 잠겨; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities #&20;](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]  
  
##  <a name="a-namelocka--csinglelocklock"></a><a name="lock"></a>CSingleLock::Lock  
 이 함수에 제공 된 동기화 개체에 의해 제어 되는 리소스에 액세스 하기를 호출 하 여 `CSingleLock` 생성자입니다.  
  
```  
BOOL Lock(DWORD dwTimeOut = INFINITE);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwTimeOut*  
 사용할 수 있는 동기화 개체에 대 한 대기 시간을 지정 합니다 (신호). 경우 **무한**, `Lock` 반환 하기 전에 개체에 신호가 전달 될 때까지 기다립니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 동기화 개체가 신호를 받으면 `Lock` 성공적으로 반환 하 고 스레드 개체를 소유 하 게 합니다. 동기화 개체가 신호 없음으로 (사용 불가) `Lock` 신호를 받을 수에 지정 된 시간 (밀리초)까지 동기화 개체에 대 한 대기는 *dwTimeOut* 매개 변수입니다. 동기화 개체는 지정 된 기간에 신호가 전송 되 되지 않은 경우 `Lock` 실패를 반환 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities #&21;](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
##  <a name="a-nameunlocka--csinglelockunlock"></a><a name="unlock"></a>CSingleLock::Unlock  
 가 소유 하는 동기화 개체를 해제 `CSingleLock`합니다.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lCount`  
 해제에 대 한 액세스 횟수입니다. 0보다 커야 합니다. 최대값을 초과 하는 개체의 수로 인해 지정 된 크기, 수는 변경 되지 않습니다 고 함수가 반환 **FALSE**합니다.  
  
 `lPrevCount`  
 이전 횟수 동기화 개체를 수신 하는 변수를 가리킵니다. 경우 **NULL**, 이전 개수가 반환 되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하 `CSingleLock`의 소멸자입니다.  
  
 두 번째 형태를 사용 하 여 둘 이상의 액세스 횟수 세마포를 해제 해야 하는 경우 `Unlock` 해제에 대 한 액세스의 수를 지정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_Utilities #&21;](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMultiLock 클래스](../../mfc/reference/cmultilock-class.md)

