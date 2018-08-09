---
title: 'Comptrrefbase:: Operator IInspectable * * 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
dev_langs:
- C++
helpviewer_keywords:
- operator IInspectable** operator
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4683305b9f7f396168bd9404f6f2501502db3d01
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645024"
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>Comptrrefbase:: Operator IInspectable\* \* 연산자

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>설명

현재 캐스팅 [ptr_](../windows/comptrrefbase-ptr-data-member.md) 데이터 멤버는 포인터--a-포인터-을는 `IInspectable` 인터페이스입니다.

오류가 발생 하는 경우에 내보내집니다 현재 **ComPtrRefBase** 에서 파생 되지 `IInspectable`합니다.

이 캐스트는 사용할 수 있는 경우에만 `__WRL_CLASSIC_COM__` 정의 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>참고 항목
[ComPtrRefBase 클래스](../windows/comptrrefbase-class.md)   
[Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)