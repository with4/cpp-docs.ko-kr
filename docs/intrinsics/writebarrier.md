---
title: _WriteBarrier | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _WriteBarrier
dev_langs:
- C++
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fda8963e89086a2b1655b7dbe3d3b95aca24a7df
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="writebarrier"></a>_WriteBarrier
**Microsoft 전용**  
  
 호출 시점 전체에서 메모리 액세스 작업을 다시 정렬할 수 있는 컴파일러 최적화를 제한합니다.  
  
> [!CAUTION]
>  `_ReadBarrier`, `_WriteBarrier` 및 `_ReadWriteBarrier` 컴파일러 내장 함수 및 `MemoryBarrier` 매크로는 모두 더 이상 사용되지 않으므로 사용하면 안 됩니다. 스레드 간 통신에 대 한 메커니즘을와 같은 사용 [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) 및 [std::atomic\<T >](../standard-library/atomic.md)에서 정의 되는 [c + + 표준 라이브러리](../standard-library/cpp-standard-library-reference.md). 하드웨어 액세스를 위해 사용 하 여는 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) 과 함께 컴파일러 옵션은 [휘발성](../cpp/volatile-cpp.md) 키워드입니다.  
  
## <a name="syntax"></a>구문  
  
```  
void _WriteBarrier(void);  
```  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`_WriteBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 `_WriteBarrier` 내장 함수는 호출 시점 전체에서 메모리 액세스 작업을 제거 또는 다시 정렬할 수 있는 컴파일러 최적화를 제한합니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_ReadBarrier](../intrinsics/readbarrier.md)   
 [_ReadWriteBarrier](../intrinsics/readwritebarrier.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [키워드](../cpp/keywords-cpp.md)