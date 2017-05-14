---
title: "_flushall | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _flushall
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
- _flushall
dev_langs:
- C++
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
caps.latest.revision: 16
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
ms.openlocfilehash: 230d52cf98e7dc563ea5d0067de7df31af8549f9
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="flushall"></a>_flushall
모든 스트림을 플러시하고 모든 버퍼를 지웁니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _flushall( void );  
```  
  
## <a name="return-value"></a>반환 값  
 `_flushall`은 열려 있는 스트림(입력 및 출력)의 수를 반환합니다. 반환되는 오류가 없습니다.  
  
## <a name="remarks"></a>설명  
 기본적으로 `_flushall` 함수는 열려 있는 출력 스트림과 연결된 모든 버퍼의 내용을 해당 파일에 씁니다. 열려 있는 입력 스트림과 연결된 모든 버퍼에서 현재 내용이 지워집니다. 이 버퍼는 대개 자동으로 디스크에 데이터를 쓸 수 있는 최적의 시간을 결정하는 운영 체제에서 유지 관리됩니다. 버퍼가 채워졌을 때 스트림이 닫히거나 스트림을 닫지 않고 프로그램이 정상적으로 종료됩니다.  
  
 `_flushall`을 호출한 후 읽는 경우 입력 파일에서 버퍼로 새 데이터를 읽습니다. `_flushall`을 호출한 후 모든 스트림이 열린 상태를 유지합니다.  
  
 런타임 라이브러리의 디스크에 커밋 기능을 사용하면 중요한 데이터가 운영 체제 버퍼 대신 디스크에 직접 기록되어 있는지 확인할 수 있습니다. 기존 프로그램을 다시 작성하지 않고 프로그램의 개체 파일을 Commode.obj에 연결하여 이 기능을 사용할 수 있습니다. 결과 실행 파일에서 `_flushall`을 호출하면 모든 버퍼의 내용이 디스크에 쓰여집니다. `_flushall` 및 `fflush`만 Commode.obj의 영향을 받습니다.  
  
 디스크에 커밋 기능을 제어하는 방법에 대한 자세한 내용은 [스트림 I/O](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md) 및 [_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_flushall`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_flushall.c  
// This program uses _flushall  
// to flush all open buffers.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int numflushed;  
  
   numflushed = _flushall();  
   printf( "There were %d streams flushed\n", numflushed );  
}  
```  
  
```Output  
There were 3 streams flushed  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [_commit](../../c-runtime-library/reference/commit.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)
