---
title: "_CrtSetReportMode | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3b5e6aedfb1cc216c621a18c74d45cdf084c5d11
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="crtsetreportmode"></a>_CrtSetReportMode
[_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [_RPT, _RPTF, _RPTW, _RPTFW 매크로](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) 및 [_RPT, _RPTF, _RPTW, _RPTFW 매크로](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)와 같이 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)를 호출하는 매크로 및 `_CrtDbgReport`에 의해 생성된 특정 보고서 형식의 대상을 지정합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
int _CrtSetReportMode(   
   int reportType,  
   int reportMode   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `reportType`  
 보고서 형식: `_CRT_WARN`, `_CRT_ERROR` 및 `_CRT_ASSERT`  
  
 `reportMode`  
 `reportType`에 대한 새 보고서 모드입니다.  
  
## <a name="return-value"></a>반환 값  
 성공적으로 완료되면 `_CrtSetReportMode`는 `reportType`에 지정된 보고서 형식에 대한 이전 보고서 모드를 반환합니다. `reportType`으로 잘못된 값이 전달되거나 `reportMode`에 대해 잘못된 모드가 지정된 경우 `_CrtSetReportMode`는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL` 로 설정하고 -1을 반환합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_CrtSetReportMode`는 `_CrtDbgReport`에 대한 출력 대상을 지정합니다. `_ASSERT`, `_ASSERTE`, `_RPT` 및 `_RPTF` 매크로가 `_CrtDbgReport`를 호출하므로 `_CrtSetReportMode`는 해당 매크로에서 지정한 텍스트의 출력 대상을 지정합니다.  
  
 [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtSetReportMode` 호출이 제거됩니다.  
  
 `_CrtSetReportMode`를 호출하여 메시지의 출력 대상을 정의하지 않으면 다음 기본값이 적용됩니다.  
  
-   어설션 실패 및 오류는 디버그 메시지 창에 전달됩니다.  
  
-   Windows 응용 프로그램의 경고는 디버거의 출력 창에 전송됩니다.  
  
-   콘솔 응용 프로그램의 경고는 표시되지 않습니다.  
  
 다음 표에는 Crtdbg.h에 정의된 보고서 형식 목록이 나와 있습니다.  
  
|보고서 형식|설명|  
|-----------------|-----------------|  
|`_CRT_WARN`|경고, 메시지 및 즉각적인 주의가 필요하지 않은 정보입니다.|  
|`_CRT_ERROR`|오류, 복구할 수 없는 문제 및 즉각적인 주의가 필요한 문제입니다.|  
|`_CRT_ASSERT`|어설션 실패(`FALSE`로 계산되는 어설션된 식)입니다.|  
  
 `_CrtSetReportMode` 함수는 `reportMode`에 지정된 새 보고서 모드를 `reportType`에 지정된 보고서 형식에 할당하고, `reportType`에 대해 이전에 정의된 보고서 모드를 반환합니다. 다음 표에는 `reportMode`에 대해 사용 가능한 선택 항목 및 `_CrtDbgReport`의 결과 동작 목록이 나와 있습니다. 이러한 옵션은 Crtdbg.h에서 비트 플래그로 정의되어 있습니다.  
  
|보고서 모드|_CrtDbgReport 동작|  
|-----------------|-----------------------------|  
|`_CRTDBG_MODE_DEBUG`|디버거의 출력 창에 메시지를 작성합니다.|  
|`_CRTDBG_MODE_FILE`|사용자가 제공한 파일 핸들에 메시지를 작성합니다. [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)을 호출하여 대상으로 사용할 특정 파일 또는 스트림을 정의해야 합니다.|  
|`_CRTDBG_MODE_WNDW`|`Abort`, `Retry` 및 `Ignore` 단추와 함께 메시지를 표시하는 메시지 상자를 만듭니다.|  
|`_CRTDBG_REPORT_MODE`|다음과 같이 지정된 `reportType`의 `reportMode`를 반환합니다.<br /><br /> 1   `_CRTDBG_MODE_FILE`<br /><br /> 2   `_CRTDBG_MODE_DEBUG`<br /><br /> 4   `_CRTDBG_MODE_WNDW`|  
  
 한 가지, 두 가지 또는 세 가지 모드를 사용하거나 모드를 전혀 사용하고 각 보고서 형식을 보고할 수 있습니다. 따라서 단일 보고서 형식에 대해 정의된 대상이 둘 이상 있을 수 있습니다. 예를 들어 다음 코드 조각을 사용하면 어설션 실패가 디버그 메시지 창과 `stderr` 둘 다에 전송됩니다.  
  
```  
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );  
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );  
```  
  
 또한 각 보고서 형식에 대한 보고 모드를 개별적으로 제어할 수 있습니다. 예를 들어 `_CRT_WARN`의 경우 `reportType`을 출력 디버그 문자열에 보내지만, 이전에 설명한 것처럼 `_CRT_ASSERT`의 경우 디버그 메시지 창을 사용하여 표시하고 reportType을 `stderr`로 보내도록 지정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportMode`|\<crtdbg.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
 **라이브러리:** 디버그 버전의 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)만 해당합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)
