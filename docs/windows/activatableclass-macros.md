---
title: ActivatableClass 매크로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
dev_langs:
- C++
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e46063bc94fae25d414d25ae67b5418ee5aa8c27
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465859"
---
# <a name="activatableclass-macros"></a>ActivatableClass 매크로

지정된 된 클래스의 인스턴스를 만들 수 있는 팩터리를 포함 하는 내부 캐시를 채웁니다.

## <a name="syntax"></a>구문

```cpp
ActivatableClass(
   className
);

ActivatableClassWithFactory(
   className,
   factory
);

ActivatableClassWithFactoryEx(
   className,
   factory,
   serverName
);
```

### <a name="parameters"></a>매개 변수

*응용 프로그램 이름*  
만들 클래스의 이름입니다.  

*팩터리*  
지정된 된 클래스의 인스턴스를 만든 팩터리입니다.

*서버 이름*  
모듈의 팩터리 하위 집합을 지정 하는 이름입니다.

## <a name="remarks"></a>설명

사용 하지 않는 경우 클래식 COM을 사용 하 여 이러한 매크로 사용 하지 마십시오 합니다 `#undef` 되도록 지시문의 **&#95; &#95;WRL_WINRT_STRICT&#95; &#95;** 매크로 정의 제거 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목
[Module 클래스](../windows/module-class.md)