---
title: "_free_locale | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _free_locale
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
- __free_locale
- free_locale
- _free_locale
dev_langs:
- C++
helpviewer_keywords:
- __free_locale function
- free_locale function
- locales, freeing
- _free_locale function
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1baa1458d3e799d2370092b7d8f96ee9fe4a359e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="freelocale"></a>_free_locale
로캘 개체를 해제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void _free_locale(  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `locale`  
 해제할 로캘 개체입니다.  
  
## <a name="remarks"></a>설명  
 `_free_locale` 함수는 `_get_current_locale` 또는 `_create_locale`에 대한 호출에서 얻은 로캘 개체를 해제하는 데 사용됩니다.  
  
 이 함수의 이전 이름인 `__free_locale`(앞에 밑줄 두 개 포함)은 사용되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|`Routine`|필수 헤더|  
|---------------|---------------------|  
|`_free_locale`|\<locale.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [_get_current_locale](../../c-runtime-library/reference/get-current-locale.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)