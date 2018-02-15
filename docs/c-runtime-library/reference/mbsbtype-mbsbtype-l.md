---
title: "_mbsbtype, _mbsbtype_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbsbtype_l
- _mbsbtype
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
dev_langs:
- C++
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e25372291d4069e2fda5130a7166b1b4da8eb525
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="mbsbtype-mbsbtypel"></a>_mbsbtype, _mbsbtype_l
문자열 내에서 바이트의 형식을 반환합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 참조 [CRT 함수는 유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _mbsbtype(  
   const unsigned char *mbstr,  
   size_t count   
);  
int _mbsbtype_l(  
   const unsigned char *mbstr,  
   size_t count,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mbstr`  
 멀티바이트 문자 시퀀스의 주소입니다.  
  
 `count`  
 문자열의 헤드로부터의 바이트 오프셋입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `_mbsbtype` 및 `_mbsbtype_l` 에 지정 된 바이트 테스트의 결과 나타내는 정수 값을 반환 합니다. 다음 표의 매니페스트 상수는 Mbctype.h에 정의됩니다.  
  
|반환 값|바이트 형식|  
|------------------|---------------|  
|`_MBC_SINGLE` (0)|싱글바이트 문자입니다. 예를 들어 코드 페이지 932에에서 `_mbsbtype` 내에 있으면 지정 된 바이트 범위 0x20-0x7E 또는 0xA1-0xDF 0을 반환 합니다.|  
|`_MBC_LEAD` (1)|멀티바이트 문자의 선행 바이트입니다. 예를 들어 코드 페이지 932에에서 `_mbsbtype` 0xFC 0x81-0x9F 또는 0xE0-범위 내에서 지정 된 바이트는 경우 1을 반환 합니다.|  
|`_MBC_TRAIL` (2)|멀티바이트 문자의 후행 바이트입니다. 예를 들어 코드 페이지 932에에서 `_mbsbtype` 0xFC 0x40-0x7E 또는 0x80-범위 내에서 지정 된 바이트는 경우 2를 반환 합니다.|  
|`_MBC_ILLEGAL` (-1)|`NULL` 문자열, 잘못된 문자 또는 `NULL` 바이트는 `mbstr`에서 `count` 오프셋에 있는 바이트 앞에 있습니다.|  
  
## <a name="remarks"></a>설명  
 `_mbsbtype` 함수는 멀티바이트 문자열에서 바이트 형식을 결정합니다. 이 함수는 `mbstr`에서 `count` 오프셋에 있는 바이트만 검사하여 지정된 바이트 앞에 있는 잘못된 문자를 무시합니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_l` 접미사가 없는 이 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하고 `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용한다는 점을 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
 입력 문자열이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno`는 `EINVAL`로 설정되고 함수는 `_MBC_ILLEGAL`을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_mbsbtype`|\<mbstring.h>|\<mbctype.h>*|  
|`_mbsbtype_l`|\<mbstring.h>|\<mbctype.h>*|  
  
 \* 매니페스트 상수에 대해 반환 값으로 사용됩니다.  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [바이트 분류](../../c-runtime-library/byte-classification.md)