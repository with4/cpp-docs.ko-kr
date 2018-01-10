---
title: "_mbsnbicmp, _mbsnbicmp_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbicmp_l
- _mbsnbicmp
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
- _strnicmp
- _wcsnicmp_l
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _tcsnicmp
- _strnicmp_l
- _tcsnicmp_l
- _wcsnicmp
- _mbsnbicmp_l
dev_langs: C++
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ba2bd2e7b4857d6c1bd57f608c20e4a2a7a85d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mbsnbicmp-mbsnbicmpl"></a>_mbsnbicmp, _mbsnbicmp_l
두 멀티바이트 문자열의 `n`바이트를 비교하고 대소문자는 무시합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int _mbsnbicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `string1, string2`  
 비교할 Null 종료 문자열입니다.  
  
 `count`  
 비교할 바이트 수입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 값은 부분 문자열 간의 관계를 나타냅니다.  
  
|반환 값|설명|  
|------------------|-----------------|  
|< 0|`string1` 부분 문자열이 `string2` 부분 문자열보다 작습니다.|  
|0|`string1` 부분 문자열이 `string2` 부분 문자열과 같습니다.|  
|> 0|`string1` 부분 문자열이 `string2` 부분 문자열보다 큽니다.|  
  
 오류 발생 시 `_mbsnbcmp`는 String.h 및 Mbstring.h에 정의된 `_NLSCMPERROR`를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_mbsnbicmp` 함수는 `count` 및 `string1`의 처음 `string2`바이트까지를 서수로 비교합니다. 각 문자를 소문자로 변환하여 비교를 수행합니다. `_mbsnbcmp`는 대소문자를 구분하는 `_mbsnbicmp` 버전입니다. `count`자를 비교하기 전에 두 문자열 중 하나에서 종결 null 문자에 도달하면 비교가 종료됩니다. `count`자를 비교하기 전에 두 문자열 중 하나에서 종결 null 문자에 도달할 때 문자열이 같으면 더 짧은 문자열이 더 작은 것으로 간주됩니다.  
  
 `_mbsnbicmp`는 문자열에서 문자가 아닌 `count` 바이트까지를 비교한다는 점을 제외하면 `_mbsnicmp`와 비슷합니다.  
  
 ASCII 테이블의 'Z'와 'a' 사이에 있는 문자('[', '\\', ']', '^', '_' 및 '\`')를 포함하는 두 문자열은 대소문자에 따라 서로 다른 방식으로 비교됩니다. 예를 들어 두 문자열 "`ABCDE`" 및 "`ABCD^`"은 소문자("`abcde`" > "`abcd^`"인 경우와 대문자("`ABCDE`" < "`ABCD^`")인 경우에 다른 방법으로 비교됩니다.  
  
 `_mbsnbicmp`는 현재 사용 중인 [멀티바이트 코드 페이지](../../c-runtime-library/code-pages.md)에 따라 멀티바이트 문자 시퀀스를 인식합니다. 현재 로캘 설정은 적용되지 않습니다.  
  
 `string1` 또는 `string2`가 null 포인터인 경우 `_mbsnbicmp`는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 함수가 `_NLSCMPERROR`를 반환하며 `errno`를 `EINVAL`로 설정합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsnicmp_l`|`_strnicmp_l`|`_mbsnbicmp_l`|`_wcsnicmp_l`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_mbsnbicmp`|<mbstring.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
 [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)에 대한 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)