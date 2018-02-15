---
title: "_get_current_locale | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _get_current_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_current_locale
- __get_current_locale
- _get_current_locale
dev_langs:
- C++
helpviewer_keywords:
- get_current_locale function
- _get_current_locale function
- locales, getting information on
- __get_current_locale function
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7199cb6cf4f0451f4607c7b9cd8a670a4d5afe2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="getcurrentlocale"></a>_get_current_locale
현재 로캘을 나타내는 로캘 개체를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
_locale_t _get_current_locale(void);  
```  
  
## <a name="return-value"></a>반환 값  
 현재 로캘을 나타내는 로캘 개체입니다.  
  
## <a name="remarks"></a>설명  
 `_get_current_locale` 함수는 현재 설정 가져옵니다 스레드에 대 한 로캘 해당 로캘을 나타내는 로캘 개체를 반환 합니다.  
  
 이 함수의 이전 이름인 `__get_current_locale`(앞에 밑줄 두 개 포함)은 사용되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_get_current_locale`|\<locale.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)