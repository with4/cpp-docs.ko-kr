---
title: "_CrtSetReportHook2, _CrtSetReportHookW2 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtSetReportHook2
- _CrtSetReportHookW2
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
- CrtSetReportHookW2
- CrtSetReportHook2
- _CrtSetReportHookW2
- _CrtSetReportHook2
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportHook2 function
- _CrtSetReportHook2 function
- _CrtSetReportHookW2 function
- CrtSetReportHookW2 function
ms.assetid: 12e5f68d-c8a7-4b1a-9a75-72ba4a8592d0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec98ae83793d2f72026bd71ea1c625069df23b7d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="crtsetreporthook2-crtsetreporthookw2"></a>_CrtSetReportHook2, _CrtSetReportHookW2
클라이언트 정의 보고 함수를 C 런타임 디버그 보고 프로세스에 후크하여 해당 함수를 설치하거나 제거합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
  
      int _CrtSetReportHook2(  
   int mode,  
   _CRT_REPORT_HOOK pfnNewHook  
);  
int _CrtSetReportHookW2(  
   int mode,  
   _CRT_REPORT_HOOKW pfnNewHook  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mode`  
 수행할 작업: `_CRT_RPTHOOK_INSTALL` 또는 `_CRT_RPTHOOK_REMOVE`  
  
 `pfnNewHook`  
 이 함수의 좁은 문자 버전에서 설치하거나 제거할 보고서 후크입니다.  
  
 `pfnNewHook`  
 이 함수의 와이드 문자 버전에서 설치하거나 제거할 보고서 후크입니다.  
  
## <a name="return-value"></a>반환 값  
 오류가 발생했으며 `EINVAL` 또는 `ENOMEM`이 설정된 경우 -1이며, 그렇지 않으면 호출한 후 `pfnNewHook`의 참조 개수를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_CrtSetReportHook2` 및 `_CrtSetReportHookW2`를 통해 함수를 후크하거나 언후크할 수 있으며 [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md)를 통해서는 함수를 후크할 수만 있습니다.  
  
 DLL에서 후크 호출이 수행될 때와 여러 DLL이 로드되고 해당 DLL 자체 후크 함수를 설정할 때 `_CrtSetReportHook` 대신 `_CrtSetReportHook2` 또는 `_CrtSetReportHookW2`를 사용해야 합니다. 이러한 경우 DLL은 로드되었을 때와 다른 순서로 언로드될 수 있으며 후크 함수는 언로드된 DLL을 가리킨 상태를 유지할 수 있습니다. 후크 함수가 `_CrtSetReportHook`와 함께 추가된 경우 디버그 출력은 프로세스를 방해합니다.  
  
 `_CrtSetReportHook2` 또는 `_CrtSetReportHookW2`를 사용하여 추가된 후크 함수가 없거나 `_CrtSetReportHook2` 및 `_CrtSetReportHookW2`를 사용하여 추가된 모든 후크 함수가 `FALSE`를 반환하는 경우 `_CrtSetReportHook`를 사용하여 추가된 후크 함수가 호출됩니다.  
  
 이 함수의 와이드 문자 버전을 사용할 수 있습니다. 보고서 후크 함수는 형식(와이드 문자 또는 좁은 문자)이 사용된 이 함수 버전과 일치하는 문자열을 사용합니다. 이 함수의 와이드 문자 버전에서 사용되는 보고서 후크에 대해 다음과 같은 함수 프로토타입을 사용합니다.  
  
```  
int YourReportHook( int reportType, wchar_t *message, int *returnValue );  
```  
  
 좁은 문자 보고서 후크에 대해 다음과 같은 프로토타입을 사용합니다.  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. `mode` 또는 `pfnNewNook`가 잘못된 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 -1을 반환합니다.  
  
> [!NOTE]
>  `/clr`을 사용하여 응용 프로그램을 컴파일했는데 응용 프로그램이 main 함수를 종료한 후 보고 함수가 호출되는 경우 보고 함수에서 CRT 함수를 호출하면 CLR에서 예외를 throw합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportHook2`|\<crtdbg.h>|\<errno.h>|  
|`_CrtSetReportHookW2`|\<crtdbg.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="example"></a>예  
  
```  
// crt_setreporthook2.c  
#include <windows.h>  
#include <stdio.h>  
#include <crtdbg.h>  
#include <assert.h>  
  
int __cdecl TestHook1(int nReportType, char* szMsg, int* pnRet)  
{  
   int nRet = FALSE;  
  
   printf("CRT report hook 1.\n");  
   printf("CRT report type is \"");  
   switch (nReportType)  
   {  
      case _CRT_ASSERT:  
      {  
         printf("_CRT_ASSERT");  
         // nRet = TRUE;   // Always stop for this type of report  
         break;  
      }  
  
      case _CRT_WARN:  
      {  
         printf("_CRT_WARN");  
         break;  
      }  
  
      case _CRT_ERROR:  
      {  
         printf("_CRT_ERROR");  
         break;  
      }  
  
      default:  
      {  
         printf("???Unknown???");  
         break;  
      }  
   }  
  
   printf("\".\nCRT report message is:\n\t");  
   printf(szMsg);  
  
   if   (pnRet)  
      *pnRet = 0;  
  
   return   nRet;  
}  
  
int __cdecl   TestHook2(int nReportType, char* szMsg, int* pnRet)  
{  
   int   nRet = FALSE;  
  
   printf("CRT report hook 2.\n");  
   printf("CRT report type is \"");  
   switch   (nReportType)  
   {  
      case _CRT_WARN:  
      {  
         printf("_CRT_WARN");  
         break;  
      }  
  
      case _CRT_ERROR:  
      {  
         printf("_CRT_ERROR");  
         break;  
      }  
  
      case _CRT_ASSERT:  
      {  
         printf("_CRT_ASSERT");  
         nRet = TRUE;   // Always stop for this type of report  
         break;  
      }  
  
      default:  
      {  
         printf("???Unknown???");  
         break;  
      }  
   }  
  
   printf("\".\nCRT report message is: \t");  
   printf(szMsg);  
  
   if   (pnRet)  
      *pnRet = 0;  
   // printf("CRT report code is %d.\n", *pnRet);  
   return   nRet;  
}  
  
int   main(int argc, char* argv[])  
{  
   int   nRet = 0;  
  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1)"  
          " returned %d\n", nRet);  
  
   _ASSERT(0);  
  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2)"  
          " returned %d\n", nRet);  
   nRet = _CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1);  
   printf("_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1)"  
          " returned %d\n", nRet);  
  
   return   nRet;  
}  
```  
  
## <a name="output"></a>출력  
  
```  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_INSTALL, TestHook1) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook2) returned 0  
_CrtSetReportHook2(_CRT_RPTHOOK_REMOVE, TestHook1) returned 0  
```  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)