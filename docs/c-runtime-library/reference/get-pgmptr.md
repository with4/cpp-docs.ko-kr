---
title: "_get_pgmptr | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_pgmptr
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
- get_pgmptr
- _get_pgmptr
dev_langs:
- C++
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: f119e7680f53f37a75b5e2e54263094e1b48a402
ms.lasthandoff: 02/24/2017

---
# <a name="getpgmptr"></a>_get_pgmptr
`_pgmptr` 전역 변수의 현재 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _get_pgmptr(   
   char **pValue   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `pValue`  
 `_pgmptr` 변수의 현재 값으로 채울 문자열에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하는 경우&0;을 반환하고, 실패하는 경우 오류 코드를 반환합니다. `pValue`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_pgmptr` 전역 변수는 프로세스와 연결된 실행 파일의 전체 경로를 포함합니다. 자세한 내용은 [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_get_pgmptr`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="net-framework-equivalent"></a>NET Framework 사용  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [_get_wpgmptr](../../c-runtime-library/reference/get-wpgmptr.md)
