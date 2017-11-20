---
title: "_ismbbtrail, _ismbbtrail_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbbtrail
- _ismbbtrail_l
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
- _ismbbtrail
- ismbbtrail
- _ismbbtrail_l
- ismbbtrail_l
dev_langs: C++
helpviewer_keywords:
- ismbbtrail_l function
- _ismbbtrail function
- _ismbbtrail_l function
- ismbbtrail function
ms.assetid: dfdd0292-960b-4c1d-bf11-146e0fc80247
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b99e318e95644b327f3629658ac5100f08c05d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ismbbtrail-ismbbtraill"></a>_ismbbtrail, _ismbbtrail_l
바이트가 멀티바이트 문자의 후행 바이트인지 여부를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _ismbbtrail(  
   unsigned int c   
);  
int _ismbbtrail_l(  
   unsigned int c,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 테스트할 정수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `_ismbbtrail`은 `c` 정수가 멀티바이트 문자의 두 번째 바이트이면 0이 아닌 값을 반환합니다. 예를 들어 코드 페이지 932에 한해 유효 범위는 0x40-0x7E 및 0x80-0xFC입니다.  
  
## <a name="remarks"></a>설명  
 `_ismbbtrail`은 로캘 종속 동작에 대해 현재 로캘을 사용합니다. `_ismbbtrail_l` 은 전달된 로캘을 대신 사용한다는 점을 제외하고 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_ismbbtrail`|\<mbctype.h> 또는 \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|  
|`_ismbbtrail_l`|\<mbctype.h> 또는 \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|  
  
 \* 테스트 조건에 대한 매니페스트 상수에 해당합니다.  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [바이트 분류](../../c-runtime-library/byte-classification.md)   
 [_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)