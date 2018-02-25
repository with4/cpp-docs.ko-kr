---
title: raw_method_prefix | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- raw_method_prefix
dev_langs:
- C++
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dc80d1468d3ac33bf7506aab98945b9c2e610e51
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="rawmethodprefix"></a>raw_method_prefix
**C + + 전용**  
  
 이름 충돌을 방지하기 위해 다른 접두사를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
raw_method_prefix("Prefix")  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Prefix`  
 사용할 접두사입니다.  
  
## <a name="remarks"></a>설명  
 하위 수준 속성과 메서드 명명 된 기본 접두사가 멤버 함수에 의해 노출 되 **raw_** 상위 수준 오류 처리 멤버 함수와 함께 이름 충돌을 피할 수 있습니다.  
  
> [!NOTE]
>  효과 `raw_method_prefix` 특성의로 변경 되지 것입니다는 [raw_interfaces_only](#_predir_raw_interfaces_only) 특성입니다. 접두사를 지정할 때 항상 `raw_method_prefix`가 `raw_interfaces_only`에 우선합니다. 두 특성 모두 동일한 `#import` 문에서 사용되는 경우 `raw_method_prefix` 특성에 의해 지정된 접두사가 사용됩니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)