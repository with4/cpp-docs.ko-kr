---
title: _setmbcp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _setmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _setmbcp
- setmbcp
dev_langs: C++
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b09953ffdb1523078f31cad08d53253b9d79892
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="setmbcp"></a>_setmbcp
새 멀티바이트 코드 페이지를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _setmbcp(  
   int codepage   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `codepage`  
 로캘 독립적인 멀티바이트 루틴에 대한 새 코드 페이지 설정입니다.  
  
## <a name="return-value"></a>반환 값  
 코드 페이지가 올바르게 설정되면 0을 반환합니다. 잘못 된 코드 페이지 값을 제공 하는 경우 `codepage`,-1 및 코드 페이지 설정이 변경 되지 않습니다. 반환 합니다. 메모리 할당 오류가 발생하면 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `_setmbcp` 함수는 새 멀티바이트 코드 페이지를 지정합니다. 기본적으로 런타임 시스템은 멀티바이트 코드 페이지를 시스템 기본 ANSI 코드 페이지로 자동 설정합니다. 멀티바이트 코드 페이지 설정은 로캘에 종속되지 않는 모든 멀티바이트 루틴에 적용됩니다. 그러나 현재 로캘에 대해 정의된 코드 페이지를 사용하도록 `_setmbcp`에 명령할 수도 있습니다. 아래의 매니페스트 상수 및 관련 동작 결과의 목록을 참조하세요. 멀티바이트 코드 페이지가 아닌 로캘 코드 페이지를 사용하는 멀티바이트 루틴의 목록은 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)을 참조하세요.  
  
 멀티바이트 코드 페이지는 다음 런타임 라이브러리 루틴의 멀티바이트 문자 처리에도 영향을 줍니다.  
  
||||  
|-|-|-|  
|[_exec 함수](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)|[_stat](../../c-runtime-library/reference/stat-functions.md)|  
|[_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[_spawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)|[_splitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)|[tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
  
 또한 `_exec` 및 `_spawn` 패밀리와 같이 멀티바이트 문자 `argv` 또는 `envp` 프로그램 인수를 매개 변수로 수신하는 모든 런타임 라이브러리 루틴은 멀티바이트 코드 페이지에 따라 이러한 문자열을 처리합니다. 따라서 이러한 루틴은 멀티바이트 코드 페이지를 변경하는 `_setmbcp`에 대한 호출의 영향도 받습니다.  
  
 `codepage` 인수는 다음 값 중 하나로 설정할 수 있습니다.  
  
-   `_MB_CP_ANSI` 프로그램을 시작할 때 운영 체제에서 가져온 ANSI 코드 페이지를 사용합니다.  
  
-   `_MB_CP_LOCALE` 이전 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 호출에서 가져온 현재 로캘의 코드 페이지를 사용합니다.  
  
-   `_MB_CP_OEM` 프로그램을 시작할 때 운영 체제에서 가져온 OEM 코드 페이지를 사용합니다.  
  
-   `_MB_CP_SBCS` 싱글바이트 코드 페이지를 사용합니다. 코드 페이지를 `_MB_CP_SBCS`로 설정하면 [_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md)와 같은 루틴은 항상 false를 반환합니다.  
  
-   그 외의 모든 유효 코드 페이지 값. 값이 ANSI인지, OEM인지 아니면 운영 체제에서 지원하는 기타 코드 페이지(지원되지 않는 UTF-7/UTF-8은 제외됨)인지는 관계가 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_setmbcp`|\<mbctype.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)