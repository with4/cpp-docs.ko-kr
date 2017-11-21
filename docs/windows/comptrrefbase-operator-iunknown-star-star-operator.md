---
title: "Comptrrefbase:: Operator IUnknown * * 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
dev_langs: C++
helpviewer_keywords: operator IUnknown** operator
ms.assetid: c2950abf-a7aa-480a-ba41-615703e7f931
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3881dbec0af43f87ff3f880da71299efdf26c64a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrrefbaseoperator-iunknown-operator"></a>ComPtrRefBase::operator IUnknown** 연산자
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
operator IUnknown**() const;  
```  
  
## <a name="remarks"></a>설명  
 현재 캐스팅 [ptr_](../windows/comptrrefbase-ptr-data-member.md) 는 포인터를-a-포인터-대상에 데이터 멤버는 IUnknown 인터페이스입니다.  
  
 현재 ComPtrRefBase IUnknown에서 파생 하지 않는 경우 오류가 발생 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [ComPtrRefBase 클래스](../windows/comptrrefbase-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)