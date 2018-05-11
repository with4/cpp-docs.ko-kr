---
title: implementation_only | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- implementation_only
dev_langs:
- C++
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a3a2cbf0b39dc1c5f5462ae105e2206d70a38f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="implementationonly"></a>implementation_only
**C + + 전용**  
  
 .tlh 헤더 파일(기본 헤더 파일)을 생성하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
implementation_only  
```  
  
## <a name="remarks"></a>설명  
 이 파일에는 형식 라이브러리 내용을 노출하는 데 사용되는 모든 선언이 포함되어 있습니다. .tli 헤더 파일이 래퍼 멤버 함수의 구현과 함께 생성되어 컴파일에 포함됩니다.  
  
 이 특성이 지정되면 .tli 헤더의 내용이 .tlh 헤더에서 일반적으로 사용되는 동일한 네임스페이스에 있습니다. 또한 멤버 함수가 인라인으로 선언되지 않습니다.  
  
 `implementation_only` 와 함께에서 사용 하기 위한 특성은 [no_implementation](../preprocessor/no-implementation.md) 미리 컴파일된 헤더 (PCH) 파일 로부터 구현을 유지 하는 방법으로는 특성입니다. `#import` 특성이 포함된 `no_implementation` 문은 PCH를 만드는 데 사용되는 소스 영역에 배치됩니다. 생성된 PCH는 많은 소스 파일에서 사용됩니다. 이 경우 `#import` 특성이 포함된 `implementation_only` 문은 PCH 영역 외부에서 사용됩니다. 소스 파일 중 하나에서 한 번만 이 문을 사용해야 합니다. 이 문을 사용하면 각 소스 파일을 추가로 다시 컴파일할 필요 없이 필요한 래퍼 멤버 함수가 모두 생성됩니다.  
  
> [!NOTE]
>  한 `implementation_only` 문의 `#import` 특성은 `#import` 특성이 포함된 동일한 형식 라이브러리의 다른 `no_implementation` 문과 함께 사용해야 합니다. 이렇게 하지 않으면 컴파일러 오류가 생성됩니다. 그 이유는 `#import` 특성이 포함된 `no_implementation` 문에서 생성된 래퍼 클래스 정의가 `implementation_only` 특성으로 생성된 구현을 컴파일하는 데 필요하기 때문입니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import 지시문](../preprocessor/hash-import-directive-cpp.md)