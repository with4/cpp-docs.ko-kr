---
title: "_get_printf_count_output | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_printf_count_output
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_printf_count_output
- _get_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: 8
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
ms.openlocfilehash: 9f45a13d9911e82b2b624689fa6b9e5eb4b20d97
ms.lasthandoff: 02/24/2017

---
# <a name="getprintfcountoutput"></a>_get_printf_count_output
[printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 패밀리 함수가 `%n` 형식을 지원하는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _get_printf_count_output();  
```  
  
## <a name="return-value"></a>반환 값  
 `%n`이 지원되는 경우 0이 아니고 `%n`이 지원되지 않는 경우 0입니다.  
  
## <a name="remarks"></a>설명  
 `%n`이 지원되지 않는 경우(기본값) `printf` 함수의 형식 문자열에서 `%n`이 나타나면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. `%n`이 지원되는 경우([_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md) 참조) `%n`은 [printf 형식 필드 문자](../../c-runtime-library/printf-type-field-characters.md)에 설명된 대로 작동합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_get_printf_count_output`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)의 예제를 참조하세요.  
  
## <a name="net-framework-equivalent"></a>NET Framework 사용  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.
