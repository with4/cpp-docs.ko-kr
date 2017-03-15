---
title: "btowc | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- btowc
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- btowc
dev_langs:
- C++
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
caps.latest.revision: 10
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
ms.openlocfilehash: ce9c4250fef70323b4e1b899efc1e5fe2e593881
ms.lasthandoff: 02/24/2017

---
# <a name="btowc"></a>btowc
초기 시프트 상태에서 정수가 유효한 싱글바이트 문자를 나타내는지 여부를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
wint_t btowc(  
   int c  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 테스트할 정수입니다.  
  
## <a name="return-value"></a>반환 값  
 초기 시프트 상태에서 정수가 유효한 싱글바이트 문자를 나타내는 경우 문자의 와이드 문자 표현을 반환합니다. 초기 시프트 상태에서 정수가 EOF이거나 유효한 싱글바이트 문자가 아닌 경우 WEOF를 반환합니다. 이 함수의 출력은 현재 `LC_TYPE` 로캘의 영향을 받습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`btowc`|\<stdio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)
