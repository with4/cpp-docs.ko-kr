---
title: "fsetpos | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: fsetpos
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
f1_keywords: fsetpos
dev_langs: C++
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71dbbf3c56f81b4987fcadb3db98be8d82e70fb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fsetpos"></a>fsetpos
스트림 위치 표시기를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int fsetpos(   
   FILE *stream,  
   const fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
 `pos`  
 위치 표시기 저장소입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `fsetpos`가 0을 반환합니다. 실패할 경우 이 함수는 0이 아닌 값을 반환하고 `errno`를 ERRNO.H에 정의된 다음 매니페스트 상수 `EBADF`(파일에 액세스할 수 없거나 `stream`이 가리키는 개체가 유효한 파일 구조체가 아님을 의미) 또는 `EINVAL`(`stream` 또는 `pos`에 대한 잘못된 값이 전달되었음을 의미) 중 하나로 설정합니다. 잘못된 매개 변수가 전달되면 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `fsetpos` 함수에 대 한 파일 위치 표시기 설정 `stream` 의 값에 `pos`, 이전 호출에서 얻을 수 있는 `fgetpos` 에 대해 `stream`합니다. 함수 파일 끝 표시기를 지우고 취소의 영향이 [ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md) 에 `stream`합니다. `fsetpos`를 호출한 후 `stream`에 대한 다음 작업은 입력 또는 출력 중 하나일 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`fsetpos`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)