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
ms.openlocfilehash: e337f6bbc92718c839fc2bd12c9df9f0caa5d5aa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883461"
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>ComPtrRefBase::operator IInspectable** 연산자

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>설명

현재 캐스팅 [ptr_](../windows/comptrrefbase-ptr-data-member.md) 데이터 멤버를 한 포인터-에-a-포인터-IInspectable 인터페이스입니다.

현재 ComPtrRefBase IInspectable에서 파생 하지 않는 경우 오류가 발생 합니다.

이 캐스트는 사용할 수 있는 경우에만 **&#95; &#95;WRL_CLASSIC_COM&#95; &#95;** 정의 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>참고 항목

[ComPtrRefBase 클래스](../windows/comptrrefbase-class.md)   
[Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)