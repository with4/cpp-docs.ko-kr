---
title: "_get_current_locale | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 13
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: e2f14ad541750967d63a50c13ec82a9ed57fce05
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

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
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_get_current_locale`|\<locale.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)
