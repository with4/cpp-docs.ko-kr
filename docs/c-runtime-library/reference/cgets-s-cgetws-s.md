---
title: "_cgets_s, _cgetws_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _cgetws_s
- _cgets_s
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cgets_s
- cgets_s
- cgetws_s
- _cgetws_s
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], getting from console
- console, getting strings from
- _cgets_s function
- cget_s function
- _cgetws_s function
- cgetws_s function
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
caps.latest.revision: 31
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
ms.openlocfilehash: 267963b8f9344cef67788726bd2c6f082c7953ac
ms.lasthandoff: 02/24/2017

---
# <a name="cgetss-cgetwss"></a>_cgets_s, _cgetws_s
콘솔에서 문자열을 가져옵니다. 이러한 버전의 [_cgets 및 _cgetws](../../c-runtime-library/cgets-cgetws.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 향상된 보안 기능이 포함되어 있습니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _cgets_s(   
   char *buffer,  
   size_t numberOfElements,  
   size_t *pSizeRead  
);  
errno_t _cgetws_s(  
   wchar_t *buffer  
   size_t numberOfElements,  
   size_t *pSizeRead  
);  
template <size_t size>  
errno_t _cgets_s(   
   char (&buffer)[size],  
   size_t *pSizeRead  
); // C++ only  
template <size_t size>  
errno_t _cgetws_s(  
   wchar_t (&buffer)[size],  
   size_t *pSizeRead  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `buffer`  
 데이터의 저장소 위치입니다.  
  
 [in] `numberOfElements`  
 단일 바이트 또는 와이드 문자 단위의 버퍼 크기이며, 읽을 수 있는 최대 문자 수이기도 합니다.  
  
 [in] `pSizeRead`  
 실제로 읽은 문자 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공할 경우 반환 값은&0;이고, 그렇지 않고 오류가 발생할 경우 오류 코드를 반환합니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`buffer`|`numberOfElements`|`pSizeRead`|반환|`buffer`의 내용|  
|--------------|------------------------|-----------------|------------|--------------------------|  
|`NULL`|any|any|`EINVAL`|해당 없음|  
|`NULL` 아님|0|모두|`EINVAL`|수정 안 됨|  
|`NULL` 아님|모두|`NULL`|`EINVAL`|빈 문자열|  
  
## <a name="remarks"></a>설명  
 `_cgets_s` 및 `_cgetws_s`는 콘솔에서 문자열을 읽고 null 종결자를 사용하여 문자열을 `buffer`에 복사합니다. `_cgetws_s`는 함수의 와이드 문자 버전이며, 문자 크기가 아니라 이러한 두 함수의 동작이 동일합니다. 읽을 수 있는 문자열의 최대 크기는 `numberOfElements` 매개 변수로 전달됩니다. 이 크기는 종료 null에 대한 추가 문자를 포함해야 합니다. 읽은 실제 문자 수는 `pSizeRead`에 배치됩니다.  
  
 작업 중이나 매개 변수의 유효성을 검사할 때 오류가 발생하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 `errno`는 `EINVAL`로 설정되고 `EINVAL`이 반환됩니다.  
  
 C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 보다 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없어지고 보안 수준이 낮은 기존 함수를 보안 수준이 높은 최신 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_cgetts_s`|`_cgets_s`|`_cgets_s`|`_cgetws_s`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_cgets_s`|\<conio.h>|  
|`_cgetws_s`|\<conio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [콘솔 및 포트 I/O](../../c-runtime-library/console-and-port-i-o.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)
