---
title: "fwrite | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fwrite
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
- fwrite
dev_langs:
- C++
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 73b5328ce6851ceb61ad3260760e95cd329ee064
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="fwrite"></a>fwrite
스트림에 데이터를 씁니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_t fwrite(  
   const void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `buffer`  
 쓸 데이터에 대한 포인터입니다.  
  
 `size`  
 항목 크기입니다(바이트).  
  
 `count`  
 쓸 항목의 최대 수입니다.  
  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `fwrite`는 정확하게 쓴 전체 항목의 수를 반환합니다. 오류가 발생하는 경우 이 수는 `count`보다 작을 수 있습니다. 또한 오류가 발생하면 파일 위치 표시기를 확인할 수 없습니다. `stream` 또는 `buffer`가 null 포인터인 경우 또는 유니코드 모드에 홀수 바이트를 쓰도록 지정한 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL` 로 설정하고 0을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `fwrite` 함수는 `count`에서 출력 `size`으로 최대 `buffer`개 항목(각 길이: `stream`)을 씁니다. `stream`(한 개가 있는 경우)과 연결된 파일 포인터는 실제로 기록된 바이트 수 만큼 증분됩니다. 경우 `stream` 열릴 텍스트 모드에서는 각 줄 바꿈은 캐리지 리턴-줄 바꿈 쌍으로 바뀝니다. 이렇게 바뀌더라도 반환 값에는 영향을 미치지 않습니다.  
  
 `stream`이 유니코드 변환 모드에서 열리는 경우(예: `stream`을 호출하고 `fopen`, `ccs=UNICODE` 또는 `ccs=UTF-16LE`이 포함된 모드 매개 변수를 사용하여 `ccs=UTF-8`을 여는 경우나 `_setmode`와 `_O_WTEXT`, `_O_U16TEXT` 또는 `_O_U8TEXT`가 포함된 모드 매개 변수를 사용하여 모드를 유니코드 변환 모드로 변경한 경우) `buffer`는 UTF-16 데이터가 포함된 `wchar_t`의 배열에 대한 포인터로 해석됩니다. 이 모드에서 홀수 바이트를 쓰려고 하면 매개 변수 유효성 검사 오류가 발생합니다.  
  
 이 함수는 호출 스레드를 잠그기 때문에 스레드로부터 안전하게 보호됩니다. 잠기지 않는 버전의 경우 `_fwrite_nolock`을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`fwrite`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
 [fread](../../c-runtime-library/reference/fread.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [_fwrite_nolock](../../c-runtime-library/reference/fwrite-nolock.md)   
 [_write](../../c-runtime-library/reference/write.md)