---
title: "__max | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __max
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
apitype: DLLExport
f1_keywords:
- max
- __max
dev_langs:
- C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
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
ms.openlocfilehash: a73c66cc0d1e49c514f8f451aa01a0c8ca7a9277
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="max"></a>__max
두 값 중 더 큰 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 숫자 데이터 형식입니다.  
  
 `a, b`  
 비교될 숫자 형식의 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `__max`는 인수 중 더 큰 숫자를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `__max` 매크로는 두 값을 비교하고 더 큰 값을 반환합니다. 인수는 서명되거나 서명되지 않은 모든 숫자 데이터 형식일 수 있습니다. 두 인수와 반환 값은 동일한 데이터 형식이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`__max`|\<stdlib.h>|  
  
## <a name="example"></a>예제  
 자세한 내용은 [__min](../../c-runtime-library/reference/min.md)에 대한 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [__min](../../c-runtime-library/reference/min.md)
