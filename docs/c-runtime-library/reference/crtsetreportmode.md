---
title: _CrtSetReportMode | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetReportMode
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
- _CrtSetReportMode
- CrtSetReportMode
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd4ac54cd4bd8877e8a6ba32f585ef5d5e29e65c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="crtsetreportmode"></a>_CrtSetReportMode

에 의해 생성 된 특정 보고서 형식에 대 한 대상을 지정 **_CrtDbgReport** 를 호출 하는 매크로 및 [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)와 같은 [_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로](assert-asserte-assert-expr-macros.md), [_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로](assert-asserte-assert-expr-macros.md), [_RPT, _RPTF, _RPTW, _RPTFW 매크로](rpt-rptf-rptw-rptfw-macros.md), 및 [_RPT, _RPTF, _RPTW, _RPTFW 매크로](rpt-rptf-rptw-rptfw-macros.md) (디버그 버전만 해당)입니다.

## <a name="syntax"></a>구문

```C
int _CrtSetReportMode(
   int reportType,
   int reportMode
);
```

### <a name="parameters"></a>매개 변수

*reportType*<br/>
보고서 종류: **_CRT_WARN**, **_CRT_ERROR**, 및 **_CRT_ASSERT**합니다.

*reportMode*<br/>
새 보고서 모드 또는 모드에 대 한 *reportType*합니다.

## <a name="return-value"></a>반환 값

성공적으로 완료 **_CrtSetReportMode** 이전 보고서 모드 또는 모드에 지정 된 보고서 형식에 대 한 반환 *reportType*합니다. 잘못 된 값으로 전달 된 경우 *reportType* 잘못 된 모드를 지정 하거나 *reportMode*, **_CrtSetReportMode** 으로 잘못 된 매개 변수 처리기가 호출 에 설명 된 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL** 하 고-1을 반환 합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**_CrtSetReportMode** 의 출력 대상을 지정 **_CrtDbgReport**합니다. 때문에 매크로 [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md), [_RPT](rpt-rptf-rptw-rptfw-macros.md), 및 [_RPTF](rpt-rptf-rptw-rptfw-macros.md) 호출 **_CrtDbgReport**, **_CrtSetReportMode** 해당 매크로 함께 지정 된 텍스트의 출력 대상을 지정 합니다.

때 [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은에 대 한 호출이 **_CrtSetReportMode** 전처리 중 제거 됩니다.

호출 하지 않으면 **_CrtSetReportMode** 메시지의 출력 대상을 정의 하려면 다음 다음과 같은 기본값 적용 됩니다.

- 어설션 실패 및 오류는 디버그 메시지 창에 전달됩니다.

- Windows 응용 프로그램의 경고는 디버거의 출력 창에 전송됩니다.

- 콘솔 응용 프로그램의 경고는 표시되지 않습니다.

다음 표에는 Crtdbg.h에 정의된 보고서 형식 목록이 나와 있습니다.

|보고서 형식|설명|
|-----------------|-----------------|
|**_CRT_WARN**|경고, 메시지 및 즉각적인 주의가 필요하지 않은 정보입니다.|
|**_CRT_ERROR**|오류, 복구할 수 없는 문제 및 즉각적인 주의가 필요한 문제입니다.|
|**_CRT_ASSERT**|어설션 실패 (계산 하는 식도 어설션 **FALSE**).|

**_CrtSetReportMode** 함수에 지정 된 새 보고서 모드를 지정 합니다. *reportMode* 에 지정 된 보고서 형식으로 *reportType* 하 고 이전에 정의한 반환 에 대 한 보고서 모드 *reportType*합니다. 다음 표에서 사용할 수 있는 항목에 대 한 *reportMode* 의 결과 동작 **_CrtDbgReport**합니다. 이러한 옵션은 Crtdbg.h에서 비트 플래그로 정의되어 있습니다.

|보고서 모드|_CrtDbgReport 동작|
|-----------------|-----------------------------|
|**_CRTDBG_MODE_DEBUG**|디버거의 출력 창에 메시지를 작성합니다.|
|**_CRTDBG_MODE_FILE**|사용자가 제공한 파일 핸들에 메시지를 작성합니다. [_CrtSetReportFile](crtsetreportfile.md)을 호출하여 대상으로 사용할 특정 파일 또는 스트림을 정의해야 합니다.|
|**_CRTDBG_MODE_WNDW**|와 함께 메시지를 표시 하는 메시지 상자를 만듭니다는 [중단](abort.md), **을 다시 시도**, 및 **무시** 단추입니다.|
|**_CRTDBG_REPORT_MODE**|반환 *reportMode* 지정 된 *reportType*:<br /><br /> 1 **_CRTDBG_MODE_FILE**<br /><br /> 2 **_CRTDBG_MODE_DEBUG**<br /><br /> 4 **_CRTDBG_MODE_WNDW**|

한 가지, 두 가지 또는 세 가지 모드를 사용하거나 모드를 전혀 사용하고 각 보고서 형식을 보고할 수 있습니다. 따라서 단일 보고서 형식에 대해 정의된 대상이 둘 이상 있을 수 있습니다. 예를 들어 다음 코드 조각 하면 어설션 실패를 모두 디버그 메시지 창이 고 보내도록 **stderr**:

```C
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );
```

또한 각 보고서 형식에 대한 보고 모드를 개별적으로 제어할 수 있습니다. 되도록 지정할 수는 예를 들어 한 *reportType* 의 **_CRT_WARN** 수을 디버그 출력 문자열에 전달 하는 동안 **_CRT_ASSERT** 되어야 디버그 메시지 창을 사용 하 여 표시 전송 **stderr**, 이전에 설명한 것입니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_CrtSetReportMode**|\<crtdbg.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

**라이브러리:** 디버그 버전의 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)만 해당합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
