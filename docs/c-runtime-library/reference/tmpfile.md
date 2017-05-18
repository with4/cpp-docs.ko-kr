---
title: tmpfile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tmpfile
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
- tmpfile
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile function
- temporary files, creating
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: efb6cd7868a393d4c946382c59b071de138ff55b
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="tmpfile"></a>tmpfile
임시 파일을 만듭니다. 더 안전한 버전을 사용할 수 있으므로 이 함수는 더 이상 사용되지 않습니다. [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
FILE *tmpfile( void );  
```  
  
## <a name="return-value"></a>반환 값  
 `tmpfile`은 정상적으로 실행되는 경우 스트림 포인터를 반환합니다. 그렇지 않으면 `NULL` 포인터를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `tmpfile` 함수는 임시 파일을 만들고 해당 스트림에 대한 포인터를 반환합니다. 임시 파일은 루트 디렉터리에 만들어집니다. 루트가 아닌 디렉터리에 임시 파일을 만들려면 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)과 함께 [tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) 또는 [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)을 사용합니다.  
  
 파일을 열 수 없는 경우 `tmpfile`은 `NULL` 포인터를 반환합니다. 현재 작업 디렉터리가 변경되지 않았다고 가정할 때 이 임시 파일은 닫거나, 프로그램이 정상적으로 종료되거나, `_rmtmp`가 호출되면 자동으로 삭제됩니다. 임시 파일은 `w+b`(이진 읽기/쓰기) 모드로 열립니다.  
  
 `tmpfile`을 사용하여 TMP_MAX(STDIO.H 참조)를 초과하는 호출을 시도하면 오류가 발생할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`tmpfile`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
> [!NOTE]
>  이 예제를 Windows Vista에서 실행하려면 관리 권한이 필요합니다.  
  
```  
// crt_tmpfile.c  
// compile with: /W3  
// This program uses tmpfile to create a  
// temporary file, then deletes this file with _rmtmp.  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  i;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      if( (stream = tmpfile()) == NULL ) // C4996  
      // Note: tmpfile is deprecated; consider using tmpfile_s instead  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
```Output  
Temporary file 1 was created  
Temporary file 2 was created  
Temporary file 3 was created  
3 temporary files deleted  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)
