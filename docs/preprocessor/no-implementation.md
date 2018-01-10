---
title: no_implementation | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_implementation
dev_langs: C++
helpviewer_keywords: no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa0a8337de519b2b0d43e8d5035e3845e1aefbe4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="noimplementation"></a>no_implementation
**C + + 전용**  
  
 래퍼 멤버 함수의 구현이 포함된 .tli 헤더를 생성하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
no_implementation  
```  
  
## <a name="remarks"></a>설명  
 이 특성이 지정된 경우 형식 라이브러리 항목을 노출하는 선언이 포함된 .tlh 헤더가 .tli 헤더 파일을 포함하는 `#include` 문 없이 생성됩니다.  
  
 이 특성은 함께에서 사용 [implementation_only](../preprocessor/implementation-only.md)합니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import 지시문](../preprocessor/hash-import-directive-cpp.md)