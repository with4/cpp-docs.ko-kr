---
title: "_get_fmode | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_fmode
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_fmode
- _get_fmode
dev_langs: C++
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 50e3ebc4e1babed323200c720722648907b42c5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="getfmode"></a>_get_fmode
파일 I/O 연산에 대한 기본 파일 변환 모드를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _get_fmode(   
   int * pmode   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `pmode`  
 현재 기본 모드로 채워질 정수에 대한 포인터: `_O_TEXT` 또는 `_O_BINARY`  
  
## <a name="return-value"></a>반환 값  
 성공하는 경우 0을 반환하고, 실패하는 경우 오류 코드를 반환합니다. `pmode`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno`는 `EINVAL`로 설정되고 함수는 `EINVAL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 [_fmode](../../c-runtime-library/fmode.md) 전역 변수의 값을 가져옵니다. 이 변수는 `_open`, `_pipe`, `fopen` 및 `freopen`과 같은 하위 수준 I/O 연산과 스트림 파일 I/O 연산 모두에 대한 기본 파일 변환 모드를 지정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_get_fmode`|\<stdlib.h>|\<fcntl.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="example"></a>예  
 [_set_fmode](../../c-runtime-library/reference/set-fmode.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [_fmode](../../c-runtime-library/fmode.md)   
 [_set_fmode](../../c-runtime-library/reference/set-fmode.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)