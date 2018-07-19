---
title: InvokeModeOptions 구조 | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b1eb0e7f6cf49a7c6ac12a4810ae1622e263e2f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882839"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions 구조

대리자 큐에 있는 모든 이벤트를 발생 시키는 하거나 오류가 발생 한 후 실행을 중지 하도록 지정 합니다. 허용 가능한 값은 지정 된 `InvokeMode` 열거형입니다.

## <a name="syntax"></a>구문

```cpp
enum InvokeMode
{
   StopOnFirstError = 1,
   FireAll = 2,
};

struct InvokeModeOptions
{
   static const InvokeMode invokeMode = invokeModeValue;
};
```

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[Microsoft:: wrl Namespace](../windows/microsoft-wrl-namespace.md)
[Microsoft::WRL::AgileEventSource 클래스](../windows/agileeventsource-class.md)