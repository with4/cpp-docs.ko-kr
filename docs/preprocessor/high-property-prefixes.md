---
title: high_property_prefixes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- high_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7df4ef6cded98c19ead86160aa772e349ebfd37
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="highpropertyprefixes"></a>high_property_prefixes
**C + + 전용**  
  
 세 가지 속성 메서드의 대체 접두사를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>매개 변수  
 `GetPrefix`  
 에 사용할 접두사는 **propget** 메서드.  
  
 `PutPrefix`  
 에 사용할 접두사는 **propput** 메서드.  
  
 `PutRefPrefix`  
 에 사용할 접두사는 **propputref** 메서드.  
  
## <a name="remarks"></a>설명  
 기본적으로 상위 수준 오류 처리 **propget**, **propput**, 및 **propputref** 메서드가 접두사로 명명 된 멤버 함수에 의해 노출 되 **가져오기** , `Put`, 및 **PutRef**각각.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)