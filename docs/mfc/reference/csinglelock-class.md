---
title: 경우 CSingleLock 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 65e969607e4017191539a0b0301b0c27ccb9f1ae
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078986"
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
|[CSingleLock::Lock](#lock)|동기화 개체에 대 한 대기 합니다.|  
|[CSingleLock::Unlock](#unlock)|동기화 개체를 해제합니다.|  
  
## <a name="remarks"></a>설명  
 `CSingleLock` 기본 클래스는 없습니다.  
  
 동기화 클래스 사용 하기 위해 [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [아니오](../../mfc/reference/ccriticalsection-class.md), 및 [CEvent](../../mfc/reference/cevent-class.md)를 하나 만들어야 합니다는 `CSingleLock` 또는 [CMultiLock](../../mfc/reference/cmultilock-class.md) 개체를 대기 하 고 동기화 개체를 해제 합니다. 사용 하 여 `CSingleLock` 때 하기만 하면 한 번에 하나의 개체에 대해 기다려야 합니다. 사용 하 여 `CMultiLock` 때 특정 시간에 사용할 수 있는 개체가 여러 개 있습니다.  
  
 사용 하는 `CSingleLock` 개체, 제어 된 리소스의 클래스에서 멤버 함수 내 해당 생성자를 호출 합니다. 그런 다음 호출에서 [IsLocked](#islocked) 멤버 함수를 리소스에 사용할 수 있는지 확인 합니다. 이 경우 나머지 멤버 함수를 계속 합니다. 리소스를 사용할 수 없는 경우 지정된 된 양의 출시 될 리소스에 대 한 시간에 대 한 대기 또는 실패를 반환 합니다. 리소스 사용을 완료 된 후 호출 하거나는 [잠금 해제](#unlock) 경우 함수는 `CSingleLock` 개체를 다시 사용 하거나 허용 하는 `CSingleLock` 개체 소멸 될 예정입니다.  
  
 `CSingleLock` 개체에서 파생 된 개체의 존재에 필요한 [CSyncObject](../../mfc/reference/csyncobject-class.md)합니다. 이것이 일반적으로 제어 되는 리소스의 클래스의 데이터 멤버입니다. 사용 하는 방법에 대 한 자세한 내용은 `CSingleLock` 개체, 문서를 참조 하십시오. [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CSingleLock`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmt.h  
  
##  <a name="csinglelock"></a>  CSingleLock::CSingleLock  
 `CSingleLock` 개체를 생성합니다.  
  
```  
explicit CSingleLock(
    CSyncObject* pObject,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *pObject*  
 에 액세스할 수 있는 동기화 개체를 가리킵니다. 일 수 없습니다 **NULL**합니다.  
  
 *bInitialLock*  
 제공된 된 개체에 액세스 하려고 처음 것인지 지정 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 일반적으로 제어 되는 리소스의 액세스 멤버 함수 내에서 호출 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]  
  
##  <a name="islocked"></a>  CSingleLock::IsLocked  
 와 관련 된 개체가 결정는 `CSingleLock` 개체를 신호 없음으로 (사용할 수 없음).  
  
```  
BOOL IsLocked();
```  
  
### <a name="return-value"></a>반환 값  
 개체가 잠겨; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]  
  
##  <a name="lock"></a>  CSingleLock::Lock  
 호출에 제공 된 동기화 개체에 의해 제어 되는 리소스에 액세스 하려면이 함수는 `CSingleLock` 생성자입니다.  
  
```  
BOOL Lock(DWORD dwTimeOut = INFINITE);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwTimeOut*  
 사용할 수 있는 동기화 개체에 대 한 대기 시간 지정 (신호). 경우 **무한**, `Lock` 반환 하기 전에 사용 하는 개체에서 신호를 보낼 때까지 기다립니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 동기화 개체가 신호를 받으면 `Lock` 성공적으로 반환 하 고 스레드가 이제 개체를 소유 합니다. 동기화 개체가 신호 없음으로 (사용 불가) `Lock` 신호를 받을 수에 지정 된 시간 (밀리초). 한도까지 동기화 개체에 대 한 대기는 *dwTimeOut* 매개 변수입니다. 동기화 개체는 지정 된 기간에 신호 되지 않은 경우 `Lock` 오류를 반환 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
##  <a name="unlock"></a>  CSingleLock::Unlock  
 가 소유 하는 동기화 개체를 해제 `CSingleLock`합니다.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *lCount*  
 해제에 대 한 액세스 횟수입니다. 0보다 커야 합니다. 지정 된 크기는 개체의 최대값을 초과 하는 횟수를 발생 시킬, 개수는 변경 되지 않습니다 및 함수 반환 **FALSE**합니다.  
  
 *lPrevCount*  
 이전 횟수 동기화 개체를 수신 하는 변수를 가리킵니다. 경우 **NULL**, 이전 개수가 반환 되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출 하 `CSingleLock`의 소멸자입니다.  
  
 둘 이상의 액세스 횟수 세마포를 해제 해야 하는 경우의 두 번째 형태를 사용 하 여 `Unlock` 해제에 대 한 액세스의 수를 지정 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMultiLock 클래스](../../mfc/reference/cmultilock-class.md)
