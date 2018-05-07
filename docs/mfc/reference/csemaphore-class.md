---
title: CSemaphore 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
dev_langs:
- C++
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f3c5f7cb354bb4889c528fc55459eabcb032709
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="csemaphore-class"></a>CSemaphore 클래스
클래스의 개체 `CSemaphore` "세마포"를 나타내는-현재 지정된 된 리소스에 액세스 하는 스레드 수 유지 관리를 액세스할 수 있는 하나 이상의 프로세스에 제한 된 수의 스레드를 허용 하는 동기화 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSemaphore : public CSyncObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSemaphore::CSemaphore](#csemaphore)|`CSemaphore` 개체를 생성합니다.|  
  
## <a name="remarks"></a>설명  
 세마포는 제한 된 사용자 수를만 지원할 수 있는 공유 리소스에 대 한 액세스를 제어 하는 데 유용 합니다. 현재 개수는 `CSemaphore` 개체에 허용 된 추가 사용자 수입니다. 에 의해 제어 되는 리소스를 사용 하려고 시도 횟수가 0, 모든는 **CSemaphore** 개체 시스템 큐에 삽입 됩니다 및 하거나 시간이 초과 될 때까지 기다리지 또는 수가 0을 초과 합니다. 제어 된 리소스를 한 번에 액세스할 수 있는 사용자의 최대 개수를 생성 하는 동안 지정한는 `CSemaphore` 개체입니다.  
  
 사용 하는 **CSemaphore** 개체를 생성 하는 `CSemaphore` 필요할 때 개체입니다. 때까지 기다렸다가 세마포의 이름을 지정 하 고 응용 프로그램에서 소유한 처음 해야 합니다. 그런 다음 생성자는 반환 될 때 세마포를 액세스할 수 있습니다. 호출 [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) 완료 되 면 제어 된 리소스에 액세스 합니다.  
  
 다른 방법을 사용 하 여 `CSemaphore` 개체 형식의 변수를 추가 하는 것 `CSemaphore` 제어 하려는 클래스를 데이터 멤버로 합니다. 제어 되는 개체의 생성 되는 동안 호출의 생성자는 `CSemaphore` 초기를 지정 하는 데이터 멤버 액세스 카운트, 최대 액세스 수, 세마포 (프로세스 경계를 넘어 사용될지) 하는 경우의 이름 및 보안 특성을 원하는 합니다.  
  
 리소스에 액세스 하 여 제어 `CSemaphore` 이 방법으로 개체는 두 가지 형식의 변수를 만들고 먼저 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 또는 형식 [CMultiLock](../../mfc/reference/cmultilock-class.md) 리소스의 액세스 멤버 함수에 있습니다. 그런 다음 잠금 개체의 호출 `Lock` 멤버 함수 (예를 들어 [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). 이 시점에서 스레드는 중 하나는 리소스에 액세스, 리소스를 해제 하 고 액세스를 하거나 출시 될 리소스 및 리소스에 액세스 실패 하는 시간이 초과 될 때까지 기다리는 합니다. 어떤 경우 든, 스레드로부터 안전한 방식으로 리소스에 액세스 합니다. 리소스를 해제 하려면 잠금 개체를 사용 하 여 `Unlock` 멤버 함수 (예를 들어 [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), 또는 범위에 속하지 않을 수 있는 잠금 개체를 허용 합니다.  
  
 만들 수 있습니다는 **CSemaphore** 독립 실행형, 개체 및 제어 된 리소스에 액세스 하기 전에 명시적으로 액세스 합니다. 자세한 내용은 소스 코드를 읽는 사람에 게 하는 동안이 메서드는 오류가 발생 하기 더 쉽습니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 **CSemaphore** 개체, 문서를 참조 하십시오. [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmt.h  
  
##  <a name="csemaphore"></a>  CSemaphore::CSemaphore  
 명명 되거나 명명 되지 않은 `CSemaphore` 개체입니다.  
  
```  
CSemaphore(
    LONG lInitialCount = 1,  
    LONG lMaxCount = 1,  
    LPCTSTR pstrName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *lInitialCount*  
 세마포에 대 한 초기 사용 횟수입니다. 0 보다 크거나 해야 보다 작거나 같음 및 `lMaxCount`합니다.  
  
 `lMaxCount`  
 세마포에 대 한 최대 사용 횟수입니다. 0보다 커야 합니다.  
  
 `pstrName`  
 세마포의 이름입니다. 세마포 프로세스 경계를 넘어 액세스할 경우에 제공 되어야 합니다. 경우 `NULL`, 개체 명명 됩니다. 생성자는 새 빌드 이름이 일치 하는 기존 세마포를 `CSemaphore` 해당 이름의 세마포를 참조 하는 개체입니다. 이름이 일치 세마포 되지 않은 기존 동기화 개체를 생성이 실패 합니다.  
  
 *lpsaAttributes*  
 Semaphore 개체에 대 한 보안 특성입니다. 에 대 한 전체 설명은이 구조를 참조 하세요. [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) Windows sdk에서입니다.  
  
### <a name="remarks"></a>설명  
 에 액세스 하거나 해제 하려면는 `CSemaphore` 개체를 만들기는 [CMultiLock](../../mfc/reference/cmultilock-class.md) 또는 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 개체와 호출 해당 [잠금](../../mfc/reference/csinglelock-class.md#lock) 및 [잠금 해제](../../mfc/reference/csinglelock-class.md#unlock) 멤버 함수입니다.  
  
> [!IMPORTANT]
>  만든 후의 `CSemaphore` 개체를 가져오려면 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 뮤텍스가 이미 존재 하지 않으면 되도록 합니다. 뮤텍스 예기치 않게 존재 않는 rogue 프로세스가 무단 점유 되 고 뮤텍스를 악의적으로 사용 하도록 의도 수를 나타낼 수 있습니다. 이 경우 보안을 중요시 위한 권장된 절차는 핸들을 종료 하 고 것 처럼 계속 개체 만들기에 오류가 발생 한 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



