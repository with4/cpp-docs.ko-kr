---
title: CComAutoDeleteCriticalSection 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b90afb9ae47ced33c331aef988489b567b1078b
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879904"
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection 클래스
이 클래스는 가져오기 및 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>설명  
 `CComAutoDeleteCriticalSection` 클래스에서 파생 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)합니다. 그러나 `CComAutoDeleteCriticalSection` 재정의 된 [용어](ccomsafedeletecriticalsection-class.md#term) 메서드를 **개인** 이 클래스의 인스턴스 범위를 벗어나는 않거나에서 명시적으로 삭제 하는 경우에 발생 하는 내부 메모리 정리를 강제 하는 액세스 메모리입니다.  

  
 이 클래스는 기본 클래스를 통해 추가 메서드가 도입 되었습니다. 참조 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) 하 고 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 임계 도우미 클래스에 대 한 자세한 내용은 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
## <a name="see-also"></a>참고 항목  
 [CComSafeDeleteCriticalSection 클래스](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 [CComCriticalSection 클래스](../../atl/reference/ccomcriticalsection-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
