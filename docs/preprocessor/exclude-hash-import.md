---
title: 제외 (#import) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- exclude
dev_langs:
- C++
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cbc9d6f5ae0dcb1f82264ff07d3ea93a71cab60
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33954130"
---
# <a name="exclude-import"></a>exclude (#import)
**C + + 전용**  
  
 생성되는 형식 라이브러리 헤더 파일에서 항목을 제외시킵니다.  
  
## <a name="syntax"></a>구문  
  
```  
exclude("Name1"[, "Name2",...])  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Name1`  
 제외시킬 첫 번째 항목입니다.  
  
 `Name2`  
 필요할 경우 제외시킬 두 번째 항목입니다.  
  
## <a name="remarks"></a>설명  
 형식 라이브러리가 시스템 헤더 또는 다른 형식 라이브러리에 정의된 항목 정의를 포함할 수 있습니다. 이 특성은 여러 개의 인수를 가질 수 있으며, 최고 수준의 형식 라이브러리 항목은 제외됩니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import 지시문](../preprocessor/hash-import-directive-cpp.md)