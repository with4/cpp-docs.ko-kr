---
title: "_ismbbkalnum, _ismbbkalnum_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ismbbkalnum
- _ismbbkalnum_l
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
- _ismbbkalnum
- ismbbkalnum
- ismbbkalnum_l
- _ismbbkalnum_l
dev_langs:
- C++
helpviewer_keywords:
- _ismbbkalnum_l function
- ismbbkalnum_l function
- _ismbbkalnum function
- ismbbkalnum function
ms.assetid: e1d70e7b-29d0-469c-9d93-442b99de22ac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: de4a09460e5c9da6aef8a9b9564c3f193bfba719
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="ismbbkalnum-ismbbkalnuml"></a>_ismbbkalnum, _ismbbkalnum_l
특정 멀티바이트 문자가 ASCII가 아닌 텍스트 기호인지 여부를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _ismbbkalnum(  
   unsigned int c   
);  
int _ismbbkalnum_l(  
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
 `_ismbbkalnum`은 `c` 정수가 문장 부호 이외의 ASCII가 아닌 텍스트 기호이면 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다. `_ismbbkalnum` 는 로캘 종속 문자 정보에 대한 현재 로캘을 사용합니다. `_ismbbkalnum_l` 은 로캘을 매개 변수로 사용한다는 점을 제외하고 `_ismbbkalnum` 과 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_ismbbkalnum`|\<mbctype.h>|  
|`_ismbbkalnum_l`|\<mbctype.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [바이트 분류](../../c-runtime-library/byte-classification.md)   
 [_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)