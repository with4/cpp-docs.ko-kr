---
title: compl | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- compl
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- std::compl
- std.compl
- compl
dev_langs:
- C++
helpviewer_keywords:
- compl function
ms.assetid: e03f6fb5-cb8b-4afa-99c0-905f4105fb34
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14d1a4d643dd18a51b7e5dd29bc8ce282be5c9ef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393676"
---
# <a name="compl"></a>compl

~ 연산자에 대한 대안입니다.

## <a name="syntax"></a>구문

```C

#define compl ~

```

## <a name="remarks"></a>설명

매크로가 ~ 연산자를 생성합니다.

## <a name="example"></a>예제

```cpp
// iso646_compl.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 1, result;

   result = ~a;
   cout << result << endl;

   result= compl(a);
   cout << result << endl;
}
```

```Output
-2
-2
```

## <a name="requirements"></a>요구 사항

**헤더:** \<iso646.h>