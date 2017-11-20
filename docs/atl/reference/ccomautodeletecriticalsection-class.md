---
title: "CComAutoDeleteCriticalSection 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs: C++
helpviewer_keywords: CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d073e392030db72d6371a798875daf3d7a90e247
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection 클래스
이 클래스는 가져오는 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>설명  
 `CComAutoDeleteCriticalSection`클래스에서 파생 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)합니다. 그러나 `CComAutoDeleteCriticalSection` 재정의 [용어](ccomsafedeletecriticalsection-class.md#term) 메서드를 `private` 액세스가이 클래스의 인스턴스 범위에서 벗어나게 않거나 메모리에서 명시적으로 삭제 하는 경우에 발생 하는 내부 메모리 정리를 강제로 수행 합니다.  

  
 이 클래스는 기본 클래스를 통해 추가 메서드가 없는 소개합니다. 참조 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) 및 [클래스](../../atl/reference/ccomcriticalsection-class.md) 임계 영역 도우미 클래스에 대 한 자세한 내용은 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [클래스](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
## <a name="see-also"></a>참고 항목  
 [CComSafeDeleteCriticalSection 클래스](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 [클래스 클래스](../../atl/reference/ccomcriticalsection-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
