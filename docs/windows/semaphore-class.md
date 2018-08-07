---
title: 클래스를 세마포 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Semaphore class
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1219c2118f9cde18fe1909a2edd02d58a4be2341
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889471"
---
# <a name="semaphore-class"></a>Semaphore 클래스
제한된 사용자 수를 지원할 수 있는 공유 리소스를 제어하는 동기화 개체를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`SyncLock`|동기 잠금을 지원 되는 클래스에 대 한 동의어입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Semaphore::Semaphore 생성자](../windows/semaphore-semaphore-constructor.md)|Semaphore 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[InvokeHelper::Invoke 메서드](../windows/invokehelper-invoke-method.md)|지정 된 인수 개수가 포함 된 시그니처 이벤트 처리기를 호출 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[Semaphore::Lock 메서드](../windows/semaphore-lock-method.md)|현재 개체 또는 지정 된 핸들과 연결 된 개체가 될 때까지 대기 신호를 받은 상태 이거나 지정한 시간 제한 간격이 경과 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[Semaphore::operator= 연산자](../windows/semaphore-operator-assign-operator.md)|Semaphore 개체에서 현재 Semaphore 개체에 지정된 된 핸들을 이동합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Semaphore`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)