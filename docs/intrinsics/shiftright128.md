---
title: __shiftright128 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __shiftright128
dev_langs: C++
helpviewer_keywords: __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 228c624c5c752a7c61178b60f8e75817fff62505
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="shiftright128"></a>__shiftright128
**Microsoft 전용**  
  
 두 개의 64비트 수량 `LowPart` 및 `HighPart`로 표현되는 128비트 수량을 `Shift`로 지정된 비트 수만큼 오른쪽으로 이동하고 결과 중 하위 64비트를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned __int64 __shiftright128(   
   unsigned __int64 LowPart,   
   unsigned __int64 HighPart,   
   unsigned char Shift   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `LowPart`  
 이동할 128비트 수량 중 하위 64비트입니다.  
  
 [in] `HighPart`  
 이동할 128비트 수량 중 상위 64비트입니다.  
  
 [in] `Shift`  
 이동할 비트 수입니다.  
  
## <a name="return-value"></a>반환 값  
 결과의 하위 64비트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__shiftright128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 `Shift` 값은 항상 64로 나눈 나머지이므로 예를 들어 `__shiftright128(0, 1, 64)`를 호출하면 함수는 상위 부분의 `0`비트를 오른쪽으로 이동하고 일반적인 경우에 반환되는 `0`이 아닌 하위 부분 `1`을 반환합니다.  
  
## <a name="example"></a>예  
 예를 들어 참조 [__shiftleft128](../intrinsics/shiftleft128.md)합니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__shiftleft128](../intrinsics/shiftleft128.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)