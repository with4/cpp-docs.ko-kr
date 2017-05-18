---
title: "_CrtDoForAllClientObjects | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDoForAllClientObjects
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
apitype: DLLExport
f1_keywords:
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
dev_langs:
- C++
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: df96a24b04473099daaca29472f90c9770181e82
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects
힙의 모든 `_CLIENT_BLOCK` 형식에 대해 응용 프로그램에서 제공하는 함수를 호출합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
void _CrtDoForAllClientObjects(   
   void ( * pfn )( void *, void * ),  
   void *context  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfn`  
 응용 프로그램에서 제공하는 함수 콜백 함수에 대한 포인터입니다. 이 함수에 대한 첫 번째 매개 변수는 데이터를 가리킵니다. 두 번째 매개 변수는 `_CrtDoForAllClientObjects`에 대한 호출로 전달되는 컨텍스트 포인터입니다.  
  
 `context`  
 응용 프로그램에서 제공하는 함수에 전달되는 응용 프로그램에서 제공하는 컨텍스트에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `_CrtDoForAllClientObjects` 함수는 형식이 `_CLIENT_BLOCK` 인 메모리 블록의 힙 연결 목록을 검색하고 이 형식의 블록을 찾으면 응용 프로그램에서 제공한 함수를 호출합니다. 찾은 블록과 `context` 매개 변수는 응용 프로그램에서 제공하는 함수에 인수로 전달됩니다. 디버깅 중 응용 프로그램은 디버그 힙 함수를 호출하여 메모리를 할당하고 해당 블록에 `_CLIENT_BLOCK` 블록 유형을 할당하도록 지정하여 특정 할당 그룹을 명시적으로 추적할 수 있습니다. 그런 다음 이러한 블록을 개별적으로 추적하여 누수 검색 및 메모리 상태 보고 시 다르게 보고할 수 있습니다.  
  
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그의 `_CRTDBG_ALLOC_MEM_DF` 비트 필드를 켜지 않은 경우 `_CrtDoForAllClientObjects`가 즉시 반환됩니다. [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtDoForAllClientObjects` 호출이 제거됩니다.  
  
 `_CLIENT_BLOCK` 형식과 다른 디버그 함수에서 이 형식을 사용하는 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.  
  
 `pfn`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속 실행하도록 허용된 경우 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)가 `EINVAL`로 설정되고 함수가 반환됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_CrtDoForAllClientObjects`|\<crtdbg.h>, \<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
 **라이브러리:** 디버그 버전의 유니버설 C 런타임 라이브러리만 해당합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)   
 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)
