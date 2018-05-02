---
title: 컴파일러 경고 (수준 1) C4052 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- C4055
dev_langs:
- C++
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29b1c8bcc836e35f7b8b81954ef247527d8ec35e
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="compiler-warning-level-1-c4055"></a>컴파일러 경고(수준 1) C4055

> '*변환*': 데이터 포인터에서 '*type1*'함수 포인터로'*type2*'

## <a name="remarks"></a>설명

**사용 되지 않는:** Visual Studio 2017 및 이후 버전에서이 경고가 생성 되지 않습니다.

데이터 포인터가 함수 포인터로 잘못 캐스팅된 것 같습니다. /Za가 지정된 경우에는 수준 1이고 /Ze가 지정된 경우에는 수준 4입니다.

## <a name="example"></a>예제

다음 샘플에서는 C4055를 생성합니다.

```C
// C4055.c
// compile with: /Za /W1 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
   return (PFUNC)pi;   // C4055
}
```

/Ze가 지정된 경우에는 이 경고가 수준 4입니다.

```C
// C4055b.c
// compile with: /W4 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
return (PFUNC)pi;   // C4055
}
```
