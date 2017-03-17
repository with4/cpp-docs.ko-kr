---
title: "CComAutoDeleteCriticalSection 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
caps.latest.revision: 17
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: eb53a0966d29759bbe7513f6042f72a280801707
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection 클래스
이 클래스는 가져오기 및 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>주의  
 `CComAutoDeleteCriticalSection`클래스에서 파생 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)합니다. 그러나 `CComAutoDeleteCriticalSection` 재정의 [용어](ccomsafedeletecriticalsection-class.md#term) 메서드를 `private` 액세스가이 클래스의 인스턴스 범위에서 벗어나게 않거나 메모리에서 명시적으로 삭제 하는 경우에 발생 하는 내부 메모리 정리를 강제로 수행 합니다.  

  
 이 클래스는 기본 클래스를 통해 추가 메서드가 없는 소개합니다. 참조 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) 및 [클래스](../../atl/reference/ccomcriticalsection-class.md) 임계 도우미 클래스에 대 한 자세한 내용은 합니다.  
  
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

