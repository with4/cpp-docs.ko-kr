---
title: "offsetof 매크로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
- offsetof
dev_langs:
- C++
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a70bb2823f29caf3f76224bfb91c3c9642bbdcf1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="offsetof-macro"></a>offsetof 매크로
부모 구조의 시작 부분에서 멤버의 오프셋을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      size_t offsetof(  
   structName,  
   memberName   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *structName*  
 부모 데이터 구조의 이름입니다.  
  
 `memberName`  
 부모 데이터 구조에서 오프셋을 결정할 멤버의 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 `offsetof`는 부모 데이터 구조에서 지정된 멤버의 오프셋(바이트)을 반환합니다. 이는 비트 필드의 경우 정의되지 않습니다.  
  
## <a name="remarks"></a>설명  
 `offsetof` 매크로는 *structName*에서 `size_t` 형식의 값으로 지정된 구조의 시작 부분에서 `memberName`의 오프셋(바이트)을 반환합니다. `struct` 키워드로 형식을 지정할 수 있습니다.  
  
> [!NOTE]
>  `offsetof`는 함수가 아니며 C 프로토타입을 사용하여 설명할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`offsetof`|\<stddef.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)