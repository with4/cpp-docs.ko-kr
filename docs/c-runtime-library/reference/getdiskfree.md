---
title: "_getdiskfree | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getdiskfree"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "getdiskfree"
  - "_getdiskfree"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_diskfree_t 형식"
  - "_getdiskfree 함수"
  - "디스크 크기"
  - "diskfree_t 형식"
  - "getdiskfree 함수"
ms.assetid: 47a3f6cf-4816-452a-8f3d-1c3ae02a0f2a
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getdiskfree
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

디스크 드라이브에 대한 정보를 사용하여 `_diskfree_t` 구조체를 채웁니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
unsigned _getdiskfree(  
   unsigned drive,  
   struct _diskfree_t * driveinfo  
);  
```  
  
#### 매개 변수  
 \[in\] `drive`  
 정보를 표시할 디스크 드라이브입니다.  
  
 \[out\] `driveinfo`  
 드라이브에 대한 정보로 채워질 `_diskfree_t` 구조체입니다.  
  
## 반환 값  
 함수가 성공할 경우 반환 값은 0입니다.  함수가 실패할 경우 반환 값은 오류 코드입니다.  운영 체제에서 반환되는 모든 오류에 대해 `errno` 값이 설정됩니다.  `errno`에 의해 표시되는 오류 조건에 대한 자세한 내용은 [errno 상수](../../c-runtime-library/errno-constants.md)를 참조하세요.  
  
## 설명  
 `_diskfree_t` 구조체는 Direct.h에 정의되어 있습니다.  
  
```  
struct _diskfree_t {   
   unsigned total_clusters;   
   unsigned avail_clusters;   
   unsigned sectors_per_cluster;   
   unsigned bytes_per_sector;   
};  
```  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  `driveinfo` 포인터가 `NULL`인 경우 또는 `drive`가 잘못된 드라이브를 지정하는 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우 함수가 `EINVAL`를 반환하며 `errno`를 `EINVAL`로 설정합니다.  올바른 드라이브의 범위는 0에서 26 사이입니다.  `drive` 값 0은 현재 드라이브를 지정합니다. 따라서 1이 드라이브 A, 3이 드라이브 C 등을 가리키는 것과 같이 숫자가 영어 알파벳 문자에 매핑됩니다.  
  
 `total_clusters`  
 디스크에서 사용된 클러스터와 사용 가능한 클러스터의 총 수입니다.  
  
 `avail_clusters`  
 디스크의 사용되지 않은 클러스터 수입니다.  
  
 `sectors_per_cluster`  
 각 클러스터의 섹터 수입니다.  
  
 `bytes_per_sector`  
 각 섹터의 크기\(바이트\)입니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_getdiskfree`|\<direct.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// crt_getdiskfree.c  
// compile with: /c  
#include <windows.h>  
#include <direct.h>  
#include <stdio.h>  
#include <tchar.h>  
  
TCHAR   g_szBorder[] = _T("======================================================================\n");  
TCHAR   g_szTitle1[] = _T("|DRIVE|TOTAL CLUSTERS|AVAIL CLUSTERS|SECTORS / CLUSTER|BYTES / SECTOR|\n");  
TCHAR   g_szTitle2[] = _T("|=====|==============|==============|=================|==============|\n");  
TCHAR   g_szLine[]   = _T("|  A: |              |              |                 |              |\n");  
  
void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal);  
  
int main(int argc, char* argv[]) {  
   TCHAR szMsg[4200];  
   struct _diskfree_t df = {0};  
   ULONG uDriveMask = _getdrives();  
   unsigned uErr, uLen, uDrive;  
  
   printf(g_szBorder);  
   printf(g_szTitle1);  
   printf(g_szTitle2);  
  
   for (uDrive=1; uDrive<=26; ++uDrive) {  
      if (uDriveMask & 1) {  
         uErr = _getdiskfree(uDrive, &df);  
         memcpy(szMsg, g_szLine, sizeof(g_szLine));  
         szMsg[3] = uDrive + 'A' - 1;  
  
         if (uErr == 0) {  
            utoiRightJustified(szMsg+8,  szMsg+19, df.total_clusters);  
            utoiRightJustified(szMsg+23, szMsg+34, df.avail_clusters);  
            utoiRightJustified(szMsg+38, szMsg+52, df.sectors_per_cluster);  
            utoiRightJustified(szMsg+56, szMsg+67, df.bytes_per_sector);  
         }  
         else {  
            uLen = FormatMessage(FORMAT_MESSAGE_FROM_SYSTEM, NULL,  
                            uErr, 0, szMsg+8, 4100, NULL);  
            szMsg[uLen+6] = ' ';  
            szMsg[uLen+7] = ' ';  
            szMsg[uLen+8] = ' ';  
         }  
  
         printf(szMsg);  
      }  
  
      uDriveMask >>= 1;  
   }  
  
   printf(g_szBorder);  
}  
  
void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal) {  
   TCHAR* szCur = szRight;  
   int nComma = 0;  
  
   if (uVal) {  
      while (uVal && (szCur >= szLeft)) {  
         if   (nComma == 3) {  
            *szCur = ',';  
            nComma = 0;  
         }  
         else {  
            *szCur = (uVal % 10) | 0x30;  
            uVal /= 10;  
            ++nComma;  
         }  
  
         --szCur;  
      }  
   }  
   else {  
      *szCur = '0';  
      --szCur;  
   }  
  
   if (uVal) {  
      szCur = szLeft;  
  
      while   (szCur <= szRight) {  
         *szCur = '*';  
         ++szCur;  
      }  
   }  
}  
```  
  
  **\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=**  
**&#124;DRIVE&#124;TOTAL CLUSTERS&#124;AVAIL CLUSTERS&#124;SECTORS \/ CLUSTER&#124;BYTES \/ SECTOR&#124;**  
**&#124;\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;**  
**&#124;  A: &#124; The device is not ready.  &#124;                 &#124;              &#124;**  
**&#124;  C: &#124;    4,721,093 &#124;    3,778,303 &#124;               8 &#124;          512 &#124;**  
**&#124;  D: &#124;    1,956,097 &#124;    1,800,761 &#124;               8 &#124;          512 &#124;**  
**&#124;  E: &#124; The device is not ready.  &#124;                 &#124;              &#124;**  
**\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=**    
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)