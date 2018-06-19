---
title: __dllonexit | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __dllonexit
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- __dllonexit
dev_langs:
- C++
helpviewer_keywords:
- __dllonexit
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c0105ccc5a40c4e5fe789814adfabe6c9749650
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450721"
---
# <a name="dllonexit"></a>__dllonexit
종료 시 호출할 루틴을 등록합니다.  
  
## <a name="syntax"></a>구문  
  
```  
_onexit_t __dllonexit(   _onexit_t func,  
   _PVFV **  pbegin,   
   _PVFV **  pend   
   )  
```  
  
#### <a name="parameters"></a>매개 변수  
 `func`  
 종료 시 실행할 함수에 대한 포인터입니다.  
  
 `pbegin`  
 삭제 시 실행할 함수 목록의 시작 부분을 가리키는 변수에 대한 포인터입니다.  
  
 `pend`  
 삭제 시 실행할 함수 목록의 끝 부분을 가리키는 변수에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공할 경우 사용자 함수에 대한 포인터입니다. 그렇지 않으면 **NULL** 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `__dllonexit` 함수는 [_onexit](../c-runtime-library/reference/onexit-onexit-m.md) 함수에서 사용되는 전역 변수가 이 루틴에 표시되지 않는다는 점을 제외하고 해당 함수와 비슷합니다. 이 함수는 전역 변수 대신 `pbegin` 및 `pend` 매개 변수를 사용합니다.  
  
 MSVCRT.LIB와 연결된 DLL에서 `_onexit` 및 `atexit` 함수는 자체 atexit/_onexit 목록을 유지해야 합니다. 이 루틴은 해당 DLL에서 호출하는 작업자입니다.  
  
 `_PVFV` 형식은 `typedef void (__cdecl *_PVFV)(void)`로 정의됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 파일|  
|-------------|-------------------|  
|__dllonexit|onexit.c|  
  
## <a name="see-also"></a>참고 항목  
 [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)