---
title: raw_interfaces_only | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_interfaces_only
dev_langs:
- C++
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4643181bf70bc92f4ef5e88b8a9add1ba7bdaad7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849303"
---
# <a name="rawinterfacesonly"></a>raw_interfaces_only
**C + + 전용**  
  
 오류 처리 래퍼 함수를 생성 하지 않습니다 및 [속성](../cpp/property-cpp.md) 이러한 래퍼 함수를 사용 하는 선언 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
raw_interfaces_only  
```  
  
## <a name="remarks"></a>설명  
 또한 `raw_interfaces_only` 특성을 사용하면 비속성 함수 명명에 사용된 기본 접두사가 제거됩니다. 접두사는 일반적으로 **raw_** 합니다. 이 특성이 지정되면 형식 라이브러리에서 직접 함수 이름을 가져옵니다.  
  
 이 특성을 사용하면 형식 라이브러리의 하위 내용만 노출할 수 있습니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import 지시문](../preprocessor/hash-import-directive-cpp.md)