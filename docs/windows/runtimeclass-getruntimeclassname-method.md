---
title: "Runtimeclass:: Getruntimeclassname 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
dev_langs: C++
helpviewer_keywords: GetRuntimeClassName method
ms.assetid: f6388163-fe65-4948-a4bc-ae6826f480e7
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c82a3ae65ae65dfe43cb0ed645f802161f7a17f6
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="runtimeclassgetruntimeclassname-method"></a>RuntimeClass::GetRuntimeClassName 메서드

현재 RuntimeClass 개체의 런타임 클래스 이름을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>매개 변수

*runtimeName*  
이 작업이 완료 될 때, 런타임 클래스 이름이 있습니다.

## <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="remarks"></a>설명

어설션 오류는 내보낸된 if / #95; &#95; WRL_STRICT &#95; #95 또는 &#95; &#95; WRL_FORCE_INSPECTABLE_CLASS_MACRO &#95; #95 정의 되지 않았습니다.

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[RuntimeClass 클래스](../windows/runtimeclass-class.md)