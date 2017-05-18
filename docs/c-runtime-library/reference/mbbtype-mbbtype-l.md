---
title: "_mbbtype, _mbbtype_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbbtype
- _mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
dev_langs:
- C++
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: e7b9c7aed7205e6cac428a0f627525f9484afc5a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="mbbtype-mbbtypel"></a>_mbbtype, _mbbtype_l
이전 바이트에 따라 바이트 형식을 반환합니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int _mbbtype(  
   unsigned char c,  
   int type   
);  
int _mbbtype_l(  
   unsigned char c,  
   int type,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 테스트할 문자입니다.  
  
 `type`  
 테스트할 바이트의 형식입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `_mbbtype`는 바이트 형식을 문자열로 반환합니다. 이 결정은 컨트롤 테스트 조건을 제공하는 `type`의 값으로 지정된 컨텍스트에 따라 다릅니다. `type`은 문자열의 이전 바이트 형식입니다. 다음 표의 매니페스트 상수는 Mbctype.h에 정의됩니다.  
  
|`type`의 값|다음에 대해 `_mbbtype` 테스트|반환 값|`c`|  
|---------------------|--------------------------|------------------|---------|  
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|`_MBC_SINGLE` (0)|단일 바이트 (0x20-0x7E, 0xA1-0xDF)|  
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|`_MBC_LEAD` (1)|멀티 바이트 문자의 바이트 (0x81-0x9F, 0xE0-0xFC)|  
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|`_MBC_ILLEGAL`<br /><br /> ( -1)|잘못 된 문자 (모든를 제외한 값 0x20-0x7E, 0xA1-0xDF, 0x81-0x9F, 0xE0-0xFC|  
|1|유효한 후행 바이트|`_MBC_TRAIL` (2)|후행 멀티 바이트 문자의 바이트 (0x40-0x7E, 0x80-0xFC)|  
|1|유효한 후행 바이트|`_MBC_ILLEGAL`<br /><br /> ( -1)|잘못 된 문자 (모든를 제외한 값 0x20-0x7E, 0xA1-0xDF, 0x81-0x9F, 0xE0-0xFC|  
  
## <a name="remarks"></a>설명  
 `_mbbtype` 함수는 멀티바이트 문자에서 바이트 형식을 결정합니다. `type` 값이 1을 제외한 모든 값이면 `_mbbtype`는 멀티바이트 문자의 유효한 단일 바이트 또는 선행 바이트가 있는지 테스트합니다. `type` 값이 1이면 `_mbbtype`는 멀티바이트 문자의 유효한 후행 바이트가 있는지 테스트합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_mbbtype` 버전의 이 함수 이 로캘 종속 동작의 현재 로캘을 사용하고 `_mbbtype_l` 버전은 전달된 로캘 매개 변수를 사용한다는 점을 제외하고는 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 이전 버전에서 `_mbbtype`의 이름은 `chkctype`입니다. 새 코드의 경우 대신 `_mbbtype`를 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_mbbtype`|\<mbstring.h>|\<mbctype.h>*|  
|`_mbbtype_l`|\<mbstring.h>|\<mbctype.h>*|  
  
 \* 반환 값으로 사용되는 매니페스트 상수의 정의에 해당합니다.  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [바이트 분류](../../c-runtime-library/byte-classification.md)
