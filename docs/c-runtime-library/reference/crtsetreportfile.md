---
title: "_CrtSetReportFile | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetReportFile
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
- CrtSetReportFile
- _CrtSetReportFile
dev_langs: C++
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8487ca011355ad248bc38c2fc2d3265f0fad4995
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile
[_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)를 사용하여 `_CRTDBG_MODE_FILE`을 지정한 이후 메시지 텍스트를 수신할 파일 핸들을 지정할 수 있습니다. `_CrtSetReportFile`은 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)에서 텍스트의 대상을 지정하는 데도 사용할 수 있습니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
_HFILE _CrtSetReportFile(   
   int reportType,  
   _HFILE reportFile   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `reportType`  
 보고서 형식: `_CRT_WARN`, `_CRT_ERROR` 및 `_CRT_ASSERT`  
  
 `reportFile`  
 `reportType`의 새 보고서 파일입니다.  
  
## <a name="return-value"></a>반환 값  
 성공적으로 완료되면 `_CrtSetReportFile`은 `reportType`에 지정된 보고서 형식에 대해 정의된 이전 보고서 파일을 반환합니다. `reportType`에 대해 잘못된 값이 전달된 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 `errno`는 `EINVAL`로 설정되고 함수는 `_CRTDBG_HFILE_ERROR`을 반환합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_CrtSetReportFile`은 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 함수와 함께 사용되어 `_CrtDbgReport`에서 생성한 특정 보고서 형식에 대한 대상을 정의합니다. `_CrtSetReportMode`가 호출되어 특정 보고서 형식에 대해 `_CRTDBG_MODE_FILE` 보고 모드를 할당하면 그다음으로 `_CrtSetReportFile`이 호출되어 대상으로 사용할 특정 파일 또는 스트림을 정의해야 합니다. [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtSetReportFile` 호출이 제거됩니다.  
  
 다음 표에는 `reportFile`에 대해 사용 가능한 선택 항목의 목록 및 `_CrtDbgReport`의 결과 동작이 나와 있습니다. 이러한 옵션은 Crtdbg.h에서 비트 플래그로 정의되어 있습니다.  
  
 `file handle`  
 메시지의 대상이 될 파일에 대한 핸들입니다. 핸들의 유효성이 확인되지는 않습니다. 파일에 대한 핸들을 열고 닫아야 합니다. 예:  
  
```  
HANDLE hLogFile;  
hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,   
   FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,   
   FILE_ATTRIBUTE_NORMAL, NULL);  
_CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_WARN, hLogFile);  
  
_RPT0(_CRT_WARN,"file message\n");  
CloseHandle(hLogFile);  
```  
  
 `_CRTDBG_FILE_STDERR`  
 `stderr`에 메시지를 작성하며, 다음과 같이 리디렉션될 수 있습니다.  
  
```  
freopen( "c:\\log2.txt", "w", stderr);  
_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);  
  
_RPT0(_CRT_ERROR,"1st message\n");  
```  
  
 `_CRTDBG_FILE_STDOUT`  
 `stdout`에 메시지를 작성하며, 사용자가 리디렉션할 수 있습니다.  
  
 `_CRTDBG_REPORT_FILE`  
 현재 보고서 모드를 반환합니다.  
  
 각 보고서 형식에 사용되는 보고서 파일을 개별적으로 제어할 수 있습니다. 예를 들어 `_CRT_ERROR`의 `reportType`은 `stderr`에 보고되도록 하고 `_CRT_ASSERT`의 `reportType`은 사용자 정의 파일 핸들 또는 스트림에 보고되도록 지정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportFile`|\<crtdbg.h>|\<errno.h>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다. 콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
 **라이브러리:** 디버그 버전의 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)만 해당합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)