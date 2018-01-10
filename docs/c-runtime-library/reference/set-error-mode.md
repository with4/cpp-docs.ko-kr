---
title: _set_error_mode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_error_mode
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_error_mode
- _set_error_mode
dev_langs: C++
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7987686fb0b9faa03cf4d5e4795116e9f0a608bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="seterrormode"></a>_set_error_mode
프로그램을 끝낼 수 있는 오류에 대해 C 런타임이 오류 메시지를 쓰는 기본이 아닌 위치를 결정하기 위해 `__error_mode`를 수정합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int _set_error_mode(  
   int modeval   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `modeval`  
 오류 메시지의 대상입니다.  
  
## <a name="return-value"></a>반환 값  
 오류가 발생하면 이전 설정 또는 -1을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `__error_mode`의 값을 설정하여 오류 출력 싱크를 제어합니다. 예를 들어 출력을 표준 오류로 보내거나 `MessageBox` API를 사용할 수 있습니다.  
  
 `modeval` 매개 변수는 다음 값 중 하나로 설정할 수 있습니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`_OUT_TO_DEFAULT`|오류 싱크가 `__app_type`에 의해 결정됩니다.|  
|`_OUT_TO_STDERR`|오류 싱크가 표준 오류입니다.|  
|`_OUT_TO_MSGBOX`|오류 싱크가 메시지 상자입니다.|  
|`_REPORT_ERRMODE`|현재 `__error_mode` 값을 보고합니다.|  
  
 나열된 값 이외의 값이 전달되면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 `_set_error_mode`은 `errno`를 `EINVAL`로 설정하고 -1을 반환합니다.  
  
 이를 [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)와 함께 사용하면 `_set_error_mode`에서 대화 상자에 실패한 문을 표시하고 사용자가 프로그램을 계속 실행할 수 있도록 `Ignore` 단추를 선택할 수 있는 옵션을 제공합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_set_error_mode`|\<stdlib.h>|  
  
## <a name="example"></a>예  
  
```C  
// crt_set_error_mode.c  
// compile with: /c  
#include <stdlib.h>  
#include <assert.h>  
  
int main()  
{  
   _set_error_mode(_OUT_TO_STDERR);  
   assert(2+2==5);  
}  
```  
  
```Output  
Assertion failed: 2+2==5, file crt_set_error_mode.c, line 8  
  
This application has requested the Runtime to terminate it in an unusual way.  
Please contact the application's support team for more information.  
```  
  
## <a name="see-also"></a>참고 항목  
 [assert Macro, _assert, _wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)