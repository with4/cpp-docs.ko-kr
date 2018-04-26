---
title: _get_purecall_handler, _set_purecall_handler | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _set_purecall_handler
- _set_purecall_handler_m
- _get_purecall_handler
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
- _set_purecall_handler
- _set_purecall_handler_m
- set_purecall_handler_m
- set_purecall_handler
- stdlib/_set_purecall_handler
- stdlib/_get_purecall_handler
- _get_purecall_handler
dev_langs:
- C++
helpviewer_keywords:
- _set_purecall_handler function
- set_purecall_handler function
- purecall_handler
- set_purecall_handler_m function
- _purecall_handler
- _set_purecall_handler_m function
- _get_purecall_handler function
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a184041e77ef6ddb97cb60a0e925ed677e2d47ba
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="getpurecallhandler-setpurecallhandler"></a>_get_purecall_handler, _set_purecall_handler

순수 가상 함수 호출에 대한 오류 처리기를 가져오거나 설정합니다.

## <a name="syntax"></a>구문

```cpp
typedef void (__cdecl* _purecall_handler)(void);
_purecall_handler __cdecl _get_purecall_handler(void);
_purecall_handler __cdecl _set_purecall_handler(
   _purecall_handler function
);
```

### <a name="parameters"></a>매개 변수

*function*<br/>
순수 가상 함수 호출 시 호출되는 함수입니다. A **_purecall_handler** 함수에 void 반환 형식이 있어야 합니다.

## <a name="return-value"></a>반환 값

이전 **_purecall_handler**합니다. 반환 **nullptr** 이전 처리기 발생 한 경우.

## <a name="remarks"></a>설명

**_get_purecall_handler** 및 **_set_purecall_handler** 함수는 Microsoft 전용 및 c + + 코드에만 적용 합니다.

순수 가상 함수에 대한 호출은 구현이 없으므로 오류입니다. 기본적으로 순수 가상 함수를 호출하면 컴파일러는 오류 처리기 함수를 호출하는 코드를 생성하므로 프로그램이 종료됩니다. 순수 가상 함수 호출을 위해 고유한 오류 처리기 함수를 설치하여 디버깅 또는 보고용으로 이러한 호출을 catch할 수 있습니다. 사용자 고유의 오류 처리기를 사용 하려면 포함 된 함수를 만들어는 **_purecall_handler** 서명을 사용 하 여 **_set_purecall_handler** 현재 처리기 되도록 합니다.

하나씩만 있기 때문에 **_purecall_handler** 호출 하는 경우 각 프로세스에 대 한 **_set_purecall_handler** 모든 스레드가 즉시 영향을 줍니다. 스레드의 마지막 호출자가 처리기를 설정합니다.

기본 동작을 복원 하려면 호출 **_set_purecall_handler** 를 사용 하 여 한 **nullptr** 인수입니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_get_purecall_handler**, **_set_purecall_handler**|\<cstdlib> 또는 \<stdlib.h>|

호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```cpp
// _set_purecall_handler.cpp
// compile with: /W1
#include <tchar.h>
#include <stdio.h>
#include <stdlib.h>

class CDerived;
class CBase
{
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function(void) = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase
{
public:
   CDerived() : CBase(this) {};   // C4355
   virtual void function(void) {};
};

CBase::~CBase()
{
   m_pDerived -> function();
}

void myPurecallHandler(void)
{
   printf("In _purecall_handler.");
   exit(0);
}

int _tmain(int argc, _TCHAR* argv[])
{
   _set_purecall_handler(myPurecallHandler);
   CDerived myDerived;
}
```

```Output
In _purecall_handler.
```

## <a name="see-also"></a>참고자료

[오류 처리](../../c-runtime-library/error-handling-crt.md)<br/>
[_purecall](purecall.md)<br/>
