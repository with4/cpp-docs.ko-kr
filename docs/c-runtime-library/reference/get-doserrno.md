---
title: "_get_doserrno | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_doserrno
- get_doserrno
dev_langs: C++
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 67f546afa3059508787c7d3a5295d2b85651f125
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="getdoserrno"></a>_get_doserrno
운영 체제에서 반환된 오류 값이 `errno` 값으로 변환되기 전에 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _get_doserrno(   
   int * pValue   
);   
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `pValue`  
 `_doserrno` 전역 매크로의 현재 값으로 채워지는 정수에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `_get_doserrno` 함수는 성공하면 0을 반환하고 실패하면 오류 코드를 반환합니다. `pValue`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 프로세스 실행을 시작하기 전에 CRT를 초기화하는 동안 `_doserrno` 전역 매크로가 0으로 설정됩니다. 운영 체제 오류를 반환하는 시스템 수준 함수 호출에 의해 반환되는 운영 체제 오류 값으로 설정되며, 실행 중 0으로 다시 설정되지 않습니다. 함수에서 반환되는 오류 값을 확인하는 코드를 작성할 때는 함수를 호출하기 전에 항상 [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md)를 사용하여 `_doserrno`를 지웁니다. 다른 함수를 호출하면 `_doserrno`를 덮어쓸 수 있으므로 함수 호출 후 바로 `_get_doserrno`를 사용하여 값을 확인합니다.  
  
 이식 가능한 오류 코드에는 `_get_doserrno` 대신 [_get_errno](../../c-runtime-library/reference/get-errno.md)를 사용하는 것이 좋습니다.  
  
 `_doserrno`의 가능한 값은 \<errno.h>에 정의되어 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_get_doserrno`|\<stdlib.h>, \<cstdlib>(C++)|\<errno.h>, \<cerrno>(C++)|  
  
 `_get_doserrno`는 Microsoft 확장입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md)   
 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)