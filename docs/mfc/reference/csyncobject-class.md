---
title: "CSyncObject 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- CSyncObject class
- synchronization classes, CSyncObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a1f0c8ddfbfaf129bb18c14d36b998dd37d35899
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="csyncobject-class"></a>CSyncObject 클래스
Win32의 동기화 개체에 일반적인 기능을 제공하는 순수 가상 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSyncObject : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSyncObject::CSyncObject](#csyncobject)|`CSyncObject` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSyncObject::Lock](#lock)|동기화 개체에 액세스 합니다.|  
|[CSyncObject::Unlock](#unlock)|동기화 개체에 액세스 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CSyncObject::operator 핸들](#operator_handle)|동기화 개체에 대 한 액세스를 제공합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CSyncObject::m_hObject](#m_hobject)|기본 동기화 개체에 대 한 핸들입니다.|  
  
## <a name="remarks"></a>주의  
 파생 된 몇 가지 클래스를 제공 하는 Microsoft Foundation Class 라이브러리 `CSyncObject`합니다. 이들은 [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [아니오](../../mfc/reference/ccriticalsection-class.md), 및 [CSemaphore](../../mfc/reference/csemaphore-class.md)합니다.  
  
 동기화 개체를 사용 하는 방법에 대 한 자세한 내용은 문서를 참조 [다중 스레딩: 동기화 클래스를 사용 하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmt.h  
  
##  <a name="csyncobject"></a>CSyncObject::CSyncObject  
 제공 된 이름으로는 동기화 개체를 생성합니다.  
  
```  
explicit CSyncObject(LPCTSTR pstrName);  
virtual ~CSyncObject();
```  
  
### <a name="parameters"></a>매개 변수  
 `pstrName`  
 개체의 이름입니다. 경우 **NULL**, *pstrName* null이 됩니다.  
  
##  <a name="lock"></a>CSyncObject::Lock  
 동기화 개체에 의해 제어 되는 리소스에 액세스 하려면이 함수를 호출 합니다.  
  
```  
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwTimeout`  
 시간 (밀리초)를 사용할 수 있는 동기화 개체에 대 한 대기 지정 (신호). 경우 **무한**, `Lock` 반환 하기 전에 개체에 신호가 전달 될 때까지 기다립니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 동기화 개체가 신호를 받으면 `Lock` 성공적으로 반환 하 고 스레드 개체를 소유 하 게 합니다. 동기화 개체가 신호 없음으로 (사용 불가) `Lock` 신호를 받을 수에 지정 된 시간 (밀리초)까지 동기화 개체에 대 한 대기는 *dwTimeOut* 매개 변수입니다. 동기화 개체는 지정 된 기간에 신호가 전송 되 되지 않은 경우 `Lock` 실패를 반환 합니다.  
  
##  <a name="m_hobject"></a>CSyncObject::m_hObject  
 기본 동기화 개체에 대 한 핸들입니다.  
  
```  
HANDLE m_hObject;  
```  
  
##  <a name="operator_handle"></a>CSyncObject::operator 핸들  
 이 연산자를 사용 하 여의 핸들을 가져올 수는 `CSyncObject` 개체입니다.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 동기화 된 개체의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 Windows Api를 직접 호출 하 여 핸들을 사용할 수 있습니다.  
  
##  <a name="unlock"></a>CSyncObject::Unlock  
 선언 `Unlock` 매개 변수 없이 순수 가상 함수가 고에서 파생 되는 모든 클래스에서 재정의 되어야 `CSyncObject`합니다.  
  
```  
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,  
    LPLONG lpPrevCount = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lCount`  
 기본 구현에서 사용 되지 않습니다.  
  
 `lpPrevCount`  
 기본 구현에서 사용 되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 기본 구현에서는 항상 반환 **TRUE**합니다.  
  
### <a name="remarks"></a>주의  
 두 개의 매개 변수를 사용 하 여 선언 항상의 기본 구현에서는 반환 **TRUE**합니다. 이 함수는 호출 스레드에서 소유 하는 동기화 개체에 대 한 액세스를 해제 하려면 호출 됩니다. 두 번째 선언 세마포 제어 된 리소스의 둘 이상의 액세스를 허용 하는 등의 동기화 개체에 제공 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




