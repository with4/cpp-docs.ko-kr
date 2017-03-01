---
title: _pclose | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _pclose
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
- _pclose
- pclose
dev_langs:
- C++
helpviewer_keywords:
- _pclose function
- pclose function
- pipes, closing
ms.assetid: e2e31a9e-ba3a-4124-bcbb-c4040110b3d3
caps.latest.revision: 14
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 33826176b57dbc26c023e0556993ade7dc3e9cfd
ms.lasthandoff: 02/24/2017

---
# <a name="pclose"></a>_pclose
새 명령 프로세서가 실행될 때까지 기다렸다가 연결된 파이프에서 스트림을 닫습니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
  
      int _pclose(  
FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 이전 `_popen`호출의 반환 값입니다.  
  
## <a name="return-value"></a>반환 값  
 종료 명령 프로세서의 종료 상태를 반환하거나, 오류가 발생하는 경우에는 -1을 반환합니다. 반환 값의 형식은 하위 바이트와 상위 바이트가 전환된다는 점을 제외하면 `_cwait`의 형식과 같습니다. 스트림이 **NULL**이면 `_pclose`는 `errno`를 `EINVAL`로 설정하고 -1을 반환합니다.  
  
 이러한 오류 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_pclose` 함수는 연결된 `_popen` 호출이 시작한 명령 프로세서(Cmd.exe)의 프로세서 ID를 조회하고, 새 명령 프로세서에 대해 [_cwait](../../c-runtime-library/reference/cwait.md)를 실행한 다음 연결된 파이프에서 스트림을 닫습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_pclose`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [_pipe](../../c-runtime-library/reference/pipe.md)   
 [_popen, _wpopen](../../c-runtime-library/reference/popen-wpopen.md)
