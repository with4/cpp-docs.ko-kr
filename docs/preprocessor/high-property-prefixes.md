---
title: high_property_prefixes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- high_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7269301fed3892fbf4b7cf6427bacb82d9712ef7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849391"
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
 [#import 지시문](../preprocessor/hash-import-directive-cpp.md)