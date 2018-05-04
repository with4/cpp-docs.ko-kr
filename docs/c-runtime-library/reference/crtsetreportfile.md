---
title: _CrtSetReportFile | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetReportFile
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
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3df4f54ad8e191dac7110a914bdde1cec888ff9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile

사용 하 여 [_CrtSetReportMode](crtsetreportmode.md) 지정 하려면 **_CRTDBG_MODE_FILE**, 수신 메시지 텍스트에 대 한 파일 핸들을 지정할 수 있습니다. **_CrtSetReportFile** 에서도 사용 되는 [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) 텍스트 (디버그 버전에만 해당)의 대상을 지정할 수 있습니다.

## <a name="syntax"></a>구문

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>매개 변수

*reportType*<br/>
보고서 종류: **_CRT_WARN**, **_CRT_ERROR**, 및 **_CRT_ASSERT**합니다.

*reportFile*<br/>
새 보고서 파일 *reportType*합니다.

## <a name="return-value"></a>반환 값

성공적으로 완료 **_CrtSetReportFile** 이전 보고서 파일에 지정 된 보고서 형식에 대해 정의 된 반환 *reportType*합니다. 잘못 된 값에 대 한 전달 된 경우 *reportType*,이 함수가 잘못 된 매개 변수 처리기를 호출 하는에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 함수가 반환 하 고 **_CRTDBG_HFILE_ERROR**합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**_CrtSetReportFile** 와 함께 사용 되는 [_CrtSetReportMode](crtsetreportmode.md) 함수에 의해 생성 된 특정 보고서 형식에 대 한 대상을 정의할 **_CrtDbgReport**합니다. 때 **_CrtSetReportMode** 할당 호출 되어는 **_CRTDBG_MODE_FILE** reporting 특정 보고서 형식에 대 한 모드 **_CrtSetReportFile** 에 호출 되어야 합니다 특정 파일 또는 대상으로 사용 하는 스트림을 정의 합니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은에 대 한 호출이 **_CrtSetReportFile** 전처리 중 제거 됩니다.

다음 목록에 대 한 사용 가능한 선택 항목에 나와 *reportFile* 의 결과 동작 **_CrtDbgReport**합니다. 이러한 옵션은 Crtdbg.h에서 비트 플래그로 정의되어 있습니다.

- **파일 핸들**

   메시지의 대상이 될 파일에 대한 핸들입니다. 핸들의 유효성이 확인되지는 않습니다. 파일에 대한 핸들을 열고 닫아야 합니다. 예를 들어:

   ```C
   HANDLE hLogFile;
   hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,
      FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,
      FILE_ATTRIBUTE_NORMAL, NULL);
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, hLogFile);

   _RPT0(_CRT_WARN,"file message\n");
   CloseHandle(hLogFile);
   ```

- **_CRTDBG_FILE_STDERR**

   메시지를 씁니다 **stderr**, 다음과 같이 리디렉션할 수 있습니다.

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   메시지를 씁니다 **stdout**를 리디렉션할 수 있는 합니다.

- **_CRTDBG_REPORT_FILE**

   현재 보고서 모드를 반환합니다.

각 보고서 형식에 사용되는 보고서 파일을 개별적으로 제어할 수 있습니다. 되도록 지정할 수는 예를 들어 한 *reportType* 의 **_CRT_ERROR** 에 보고 될 **stderr**, 동안는 *reportType* 의 **_CRT_ASSERT** 사용자 정의 파일 핸들 또는 스트림에 보고 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h>|\<errno.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 응용 프로그램에서 지원 되지 않습니다. 콘솔을 사용 하는 연결 된 표준 스트림 핸들 **stdin**, **stdout**, 및 **stderr**, C 런타임 함수 UWP 앱에서 사용할 수 있는 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

**라이브러리:** 디버그 버전의 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)만 해당합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
