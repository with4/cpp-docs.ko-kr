---
title: "fgets, fgetws | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fgets
- fgetws
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
- _fgetts
- fgetws
- fgets
dev_langs:
- C++
helpviewer_keywords:
- _fgetts function
- streams, getting strings from
- streams, reading from
- fgets function
- fgetws function
- fgetts function
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 4012de79c3de0a27837813ddddf8b7e1aec4fac7
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="fgets-fgetws"></a>fgets, fgetws
스트림에서 문자열을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
char *fgets(   
   char *str,  
   int n,  
   FILE *stream   
);  
wchar_t *fgetws(   
   wchar_t *str,  
   int n,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `str`  
 데이터의 저장소 위치입니다.  
  
 `n`  
 읽을 최대 문자 수입니다.  
  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이러한 각 함수는 `str`를 반환합니다. `NULL`은 오류 또는 파일 끝 조건을 나타내기 위해 반환됩니다. 오류가 발생했는지 여부를 확인하려면 `feof` 또는 `ferror`를 사용합니다. `str` 또는 `stream`이 null 포인터이거나 `n`이 0보다 작거나 같으면 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정되고 함수는 `NULL`을 반환합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `fgets` 함수는 입력 `stream` 인수에서 문자열을 읽어 `str`에 저장합니다. `fgets`첫 번째 줄 바꿈 문자 나타날 경우 현재 스트림 위치에서 읽은 문자 수가 같은지를 때까지 또는 스트림의 끝에 문자를 읽고 `n` -1 중 하나에 먼저 합니다. `str`에 저장된 결과는 null 문자와 함께 추가됩니다. 줄 바꿈 문자는 읽을 경우 문자열에 포함됩니다.  
  
 `fgetws`는 `fgets`의 와이드 문자 버전입니다.  
  
 `fgetws`는 `str`이 텍스트 모드로 열리는지, 아니면 이진 모드로 열리는지에 따라 와이드 문자 인수 `stream`을 각각 멀티바이트 문자열 또는 와이드 문자열로 읽습니다. 텍스트 및 이진 모드를 유니코드 및 멀티바이트 스트림 I/O에서 사용하는 방법에 대한 자세한 내용은 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 및 [텍스트 및 이진 모드의 유니코드 스트림 I/O](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_fgetts`|`fgets`|`fgets`|`fgetws`|  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`fgets`|\<stdio.h>|  
|`fgetws`|\<stdio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_fgets.c  
// This program uses fgets to display  
// a line from a file on the screen.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[100];  
  
   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )  
   {  
      if( fgets( line, 100, stream ) == NULL)  
         printf( "fgets error\n" );  
      else  
         printf( "%s", line);  
      fclose( stream );  
   }  
}  
```  
  
## <a name="input-crtfgetstxt"></a>입력 crt_fgets.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>출력  
  
```  
Line one.  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [gets, _getws](../../c-runtime-library/gets-getws.md)   
 [puts, _putws](../../c-runtime-library/reference/puts-putws.md)
