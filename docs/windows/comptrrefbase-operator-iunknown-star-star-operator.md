---
title: 'Comptrrefbase:: Operator IUnknown * * 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
dev_langs:
- C++
helpviewer_keywords:
- operator IUnknown** operator
ms.assetid: c2950abf-a7aa-480a-ba41-615703e7f931
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 816c71d2c14b373e63de2b2c8725eb87b40d91e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870317"
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