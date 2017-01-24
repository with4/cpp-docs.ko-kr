---
title: "_CrtSetReportHook2, _CrtSetReportHookW2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportHook2"
  - "_CrtSetReportHookW2"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CrtSetReportHookW2"
  - "CrtSetReportHook2"
  - "_CrtSetReportHookW2"
  - "_CrtSetReportHook2"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtSetReportHook2 함수"
  - "_CrtSetReportHook2 함수"
  - "_CrtSetReportHookW2 함수"
  - "CrtSetReportHookW2 함수"
ms.assetid: 12e5f68d-c8a7-4b1a-9a75-72ba4a8592d0
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtSetReportHook2, _CrtSetReportHookW2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C 런타임 디버그 보고 프로세스 \(디버그 버전에만 해당\)에 연결하여 클라이언트 정의 보고 함수를 설치하거나 삭제합니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 `mode`  
 수행할 동작입니다 : `_CRT_RPTHOOK_INSTALL` 또는 `_CRT_RPTHOOK_REMOVE`.  
  
 `pfnNewHook`  
 이 함수의 좁은 문자 버전에서 보고서 후크를 설치하거나 제거합니다.  
  
 `pfnNewHook`  
 이 함수의 넓은 문자 버전에서 보고서 후크를 설치하거나 제거합니다.  
  
## 반환 값  
 오류가 `EINVAL` 또는 `ENOMEM` 세트로 발생했을 경우 \-1 , 그렇지 않으면 `pfnNewHook` 의 참조 카운트는 호출 후 반환 됩니다.  
  
## 설명  
 `_CrtSetReportHook2` 및 `_CrtSetReportHookW2`  은 함수를 연결하거나 풉니다. [\_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md) 만 함수를 연결할 수 있습니다.  
  
 `_CrtSetReportHook2` 또는 `_CrtSetReportHookW2`  는 여러개의 DLL이 로드 되고 후크 함수 자체를 설정할 때와 DLL 에서 후크 호출이 이루어 질 때 `_CrtSetReportHook` 대신에 사용 됩니다.  이러한 상황에서, DLL은 그들이로드 된 것과 다른 순서로 언로드 될 수 있으며, 후크 함수는 언로드 DLL을 가리키는 채 남아있을 수 있습니다.  후크 함수가 `_CrtSetReportHook` 를 사용하여 추가 된 경우, 디버그는 프로세스에 캐쉬를 출력 합니다.  
  
 `_CrtSetReportHook2` 또는 `_CrtSetReportHookW2`  을 사용하여 추가 된 후크 함수가 없는 경우 또는 모든 후크 함수가 `_CrtSetReportHook2` 및 `_CrtSetReportHookW2`  을 사용하여 추가된 경우에 호출 되는 `_CrtSetReportHook` 를 사용하여 추가 된 후크 함수는 `FALSE` 를 반환합니다.  
  
 이 함수의 와이드 문자 버전은 이용 가능합니다.  보고서 후크 함수는 \(좁은 또는 와이드 문자\) 형식의 이 함수를 사용하는 버전과 일치 해야 문자열을 허용 합니다.  이 함수의 와이드 문자 버전에서 사용하는 보고서 후크에 대해 다음 함수 프로토 타입을 사용합니다 :  
  
```  
int YourReportHook( int reportType, wchar_t *message, int *returnValue );  
```  
  
 좁은 문자 보고서 후크에 대해 다음과 같은 프로토 타입을 사용합니다 :  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다.   `mode` 또는 `pfnNewNook` 가 잘못된 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EINVAL` 로 설정하고 \-1을 반환합니다.  
  
> [!NOTE]
>  응용 프로그램이  `/clr` 로 컴파일되거나 보고 함수가 응용 프로그램이 종료될 때 호출될 떄,  보고 함수가 CRT 함수를 호출 하면 CLR은 예외를 throw 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_CrtSetReportHook2`|\<crtdbg.h\>|\<\<errno.h\>\>|  
|`_CrtSetReportHookW2`|\<crtdbg.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 예제  
  
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
  
## Output  
  
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
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)