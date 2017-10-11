---
title: towctrans | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- towctrans
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- towctrans
dev_langs:
- C++
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: fcd97b3af0bb7e469db18b1a7ff8290af5df1bc4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="towctrans"></a>towctrans
문자를 변형합니다.  
  
## <a name="syntax"></a>구문  
  
```  
wint_t towctrans(  
   wint_t c,  
   wctrans_t category   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 변형할 문자입니다.  
  
 `category`  
 [wctrans](../../c-runtime-library/reference/wctrans.md)의 반환 값을 포함하는 식별자입니다.  
  
## <a name="return-value"></a>반환 값  
 `c` 다음의 문자 `towctrans`가 `category`에서 변환 규칙을 사용했습니다.  
  
## <a name="remarks"></a>설명  
 `category`의 값은 이전에 정상적으로 수행한 [wctrans](../../c-runtime-library/reference/wctrans.md) 호출에 의해 이미 반환된 상태여야 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`towctrans`|\<wctype.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 `wctrans`를 사용하는 샘플은 `towctrans`를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)
