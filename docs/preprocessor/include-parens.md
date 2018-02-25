---
title: include() | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- include()
dev_langs:
- C++
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da6a8bfc67f63caa8ee1f2699c8bb8675dbae775
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="include"></a>include()
**C + + 전용**  
  
 자동 제외를 사용하지 않도록 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
include("Name1"[,"Name2", ...])  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Name1`  
 강제로 포함할 첫 번째 항목입니다.  
  
 `Name2`  
 필요할 경우 강제로 포함할 두 번째 항목입니다.  
  
## <a name="remarks"></a>설명  
 형식 라이브러리가 시스템 헤더 또는 다른 형식 라이브러리에 정의된 항목 정의를 포함할 수 있습니다. `#import`는 다양한 정의 오류를 자동으로 제외하여 해당 오류를 방지하려고 합니다. 항목 제외 되는, 나타내듯이 경우 [컴파일러 경고 (수준 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md), 권한이 없어야 하 고 되 면 자동 제외 하지 않으려면이 특성을 사용할 수 있습니다. 이 특성은 각각 포함할 형식 라이브러리 항목의 이름이 될 인수 몇 개를 가질 수 있습니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)