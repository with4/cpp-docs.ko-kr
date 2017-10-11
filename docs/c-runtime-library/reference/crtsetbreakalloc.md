---
title: "_CrtSetBreakAlloc | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtSetBreakAlloc
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
- CrtSetBreakAlloc
- _CrtSetBreakAlloc
dev_langs:
- C++
helpviewer_keywords:
- CrtSetBreakAlloc function
- _CrtSetBreakAlloc function
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: a11b7847e83a129099e0f54cccce35032cf68fe4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="crtsetbreakalloc"></a>_CrtSetBreakAlloc
지정된 개체 할당 순서 번호에 대한 중단점을 설정합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
  
      long _CrtSetBreakAlloc(   
   long lBreakAlloc   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *lBreakAlloc*  
 중단점을 설정할 할당 순서 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 중단점이 설정된 이전 개체 할당 순서 번호를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_CrtSetBreakAlloc`은 응용 프로그램에서 메모리 할당의 특정 지점에서 중단한 다음 요청의 원점으로 다시 추적하여 메모리 누수 검색을 수행하도록 허용합니다. 메모리 블록에 할당된 순차적 개체 할당 순서 번호가 힙에서 할당된 경우 이 함수는 이 번호를 사용합니다. [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtSetBreakAlloc` 호출이 제거됩니다.  
  
 Crtdbg.h에 정의된 대로 개체 할당 순서 번호는 **_CrtMemBlockHeader** 구조체의 *lRequest* 필드에 저장됩니다. 디버그 덤프 함수 중 하나가 메모리 블록에 대한 정보를 보고하면 이 번호는 중괄호로 묶어 표시합니다(예: {36}).  
  
 다른 메모리 관리 함수와 함께 `_CrtSetBreakAlloc`을 사용하는 방법에 대한 자세한 내용은 [힙 할당 요청 추적](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_CrtSetBreakAlloc`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_setbrkal.c  
// compile with: -D_DEBUG /MTd -Od -Zi -W3 /c /link -verbose:lib -debug  
  
/*  
 * In this program, a call is made to the _CrtSetBreakAlloc routine  
 * to verify that the debugger halts program execution when it reaches  
 * a specified allocation number.  
 */  
  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( )  
{  
        long allocReqNum;  
        char *my_pointer;  
  
        /*   
         * Allocate "my_pointer" for the first  
         * time and ensure that it gets allocated correctly  
         */  
        my_pointer = malloc(10);  
        _CrtIsMemoryBlock(my_pointer, 10, &allocReqNum, NULL, NULL);  
  
        /*   
         * Set a breakpoint on the allocation request  
         * number for "my_pointer"  
         */  
        _CrtSetBreakAlloc(allocReqNum+2);  
  
        /*   
         * Alternate freeing and reallocating "my_pointer"  
         * to verify that the debugger halts program execution  
         * when it reaches the allocation request  
         */  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)
