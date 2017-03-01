---
title: "_isatty | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _isatty
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
- _isatty
dev_langs:
- C++
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
caps.latest.revision: 18
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
ms.openlocfilehash: dbffe7023e178949f7167f283107e147ed13cb66
ms.lasthandoff: 02/24/2017

---
# <a name="isatty"></a>_isatty
파일 설명자가 문자 장치와 연결되어 있는지 여부를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      int _isatty(  
int fd   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fd`  
 테스트할 장치를 나타내는 파일 설명자입니다.  
  
## <a name="return-value"></a>반환 값  
 `_isatty`는 설명자가 문자 장치와 연결된 경우&0;이 아닌 값을 반환합니다. 그렇지 않으면 `_isatty`는 0을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_isatty` 함수는 `fd`가 문자 장치(터미널, 콘솔, 프린터 또는 직렬 포트)와 연결되어 있는지 여부를 확인합니다.  
  
 이 함수는 `fd` 매개 변수의 유효성을 검사합니다. `fd`가 잘못된 파일 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 함수는 0을 반환하고 `errno`를 `EBADF`로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_isatty`|\<io.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_isatty.c  
/* This program checks to see whether  
 * stdout has been redirected to a file.  
 */  
  
#include <stdio.h>  
#include <io.h>  
  
int main( void )  
{  
   if( _isatty( _fileno( stdout ) ) )  
      printf( "stdout has not been redirected to a file\n" );  
   else  
      printf( "stdout has been redirected to a file\n");  
}  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
stdout has not been redirected to a file  
```  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)
