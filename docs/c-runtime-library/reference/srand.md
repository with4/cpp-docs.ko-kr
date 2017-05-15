---
title: srand | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- srand
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- srand
dev_langs:
- C++
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.assetid: 7bf56dc5-5692-4182-a3c1-18af98d2dd1a
caps.latest.revision: 12
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e86ea8aa561af584a6825d4225820aca7baeced2
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="srand"></a>srand
의사 난수 생성기에 대한 시작 시드 값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void srand(  
   unsigned int seed   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `seed`  
 의사 난수 생성을 위한 시드  
  
## <a name="remarks"></a>설명  
 `srand` 함수는 현재 스레드에서 일련의 의사 난수 정수 생성을 위한 시작점을 설정합니다. 같은 결과 시퀀스를 만들도록 생성기를 다시 초기화하려면 `srand` 함수를 사용하고 같은 `seed` 인수를 다시 사용합니다. `seed`에 대해 다른 모든 값을 사용하면 생성기가 의사 난수 시퀀스에서 다른 시작점으로 설정됩니다. `rand`는 생성된 의사 난수를 검색합니다. `srand`를 호출하기 전에 `rand`를 호출하면 1로 전달된 `seed`를 사용하여 `srand`를 호출할 때와 같은 시퀀스가 생성됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`srand`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [rand](../../c-runtime-library/reference/rand.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [rand](../../c-runtime-library/reference/rand.md)
