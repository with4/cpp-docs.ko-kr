---
title: _getdiskfree | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _getdiskfree
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- getdiskfree
- _getdiskfree
dev_langs:
- C++
helpviewer_keywords:
- diskfree_t type
- _getdiskfree function
- _diskfree_t type
- disk size
- getdiskfree function
ms.assetid: 47a3f6cf-4816-452a-8f3d-1c3ae02a0f2a
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23301ec8ffc7868da9d14dd22439e9915e21ecdf
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="getdiskfree"></a>_getdiskfree

사용 하 여 디스크 드라이브에 대 한 정보는 **_diskfree_t** 구조입니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
unsigned _getdiskfree(
   unsigned drive,
   struct _diskfree_t * driveinfo
);
```

### <a name="parameters"></a>매개 변수

*드라이브*<br/>
정보를 표시할 디스크 드라이브입니다.

*driveinfo*<br/>
A **_diskfree_t** 구조는 드라이브에 대 한 정보로 채울 수입니다.

## <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 0입니다. 함수가 실패할 경우 반환 값은 오류 코드입니다. 값 **errno** 운영 체제에 의해 반환 되는 모든 오류에 대해 설정 됩니다. 으로 표시 된 오류 조건에 대 한 자세한 내용은 **errno**, 참조 [errno 상수](../../c-runtime-library/errno-constants.md)합니다.

## <a name="remarks"></a>설명

**_diskfree_t** 구조체는 Direct.h에 정의 됩니다.

```C
struct _diskfree_t {
   unsigned total_clusters;      // The total number of clusters, both used and available, on the disk.
   unsigned avail_clusters;      // The number of unused clusters on the disk.
   unsigned sectors_per_cluster; // The number of sectors in each cluster.
   unsigned bytes_per_sector;    // The size of each sector in bytes.
};
```

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우는 *driveinfo* 포인터가 **NULL** 또는 *드라이브* 잘못 된 드라이브를 지정 합니다.이 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 계속 하려면 실행 허용 된 경우, 함수 반환 **EINVAL** 설정 **errno** 를 **EINVAL**합니다. 올바른 드라이브의 범위는 0에서 26 사이입니다. A *드라이브* 현재 드라이브를 지정 하는 값이 0 됩니다; 그 후 숫자 매핑됩니다 이러한 영어 알파벳의 1이 드라이브 A, 3 드라이브 C 등 나타냅니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_getdiskfree**|\<direct.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
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

```Output
======================================================================
|DRIVE|TOTAL CLUSTERS|AVAIL CLUSTERS|SECTORS / CLUSTER|BYTES / SECTOR|
|=====|==============|==============|=================|==============|
|  A: | The device is not ready.    |                 |              |
|  C: |    4,721,093 |    3,778,303 |               8 |          512 |
|  D: |    1,956,097 |    1,800,761 |               8 |          512 |
|  E: | The device is not ready.    |                 |              |
======================================================================
```

## <a name="see-also"></a>참고자료

[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
