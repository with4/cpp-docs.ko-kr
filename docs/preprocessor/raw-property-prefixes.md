---
title: raw_property_prefixes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_property_prefixes
dev_langs: C++
helpviewer_keywords: raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 190a7ce7fbca4fea477771b5c125c96ecc187216
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes
**C + + 전용**  
  
 세 가지 속성 메서드의 대체 접두사를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>매개 변수  
 `GetPrefix`  
 에 사용할 접두사는 **propget** 메서드.  
  
 `PutPrefix`  
 에 사용할 접두사는 **propput** 메서드.  
  
 `PutRefPrefix`  
 에 사용할 접두사는 **propputref** 메서드.  
  
## <a name="remarks"></a>설명  
 기본적으로 낮은 수준의 **propget**, **propput**, 및 **propputref** 메서드가의 접두사로 명명 된 멤버 함수에 의해 노출 되 **get_**, **put_**, 및 **putref_** 각각. 이 접두사는 MIDL로 생성한 헤더 파일에 사용되는 이름과 호환됩니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import 지시문](../preprocessor/hash-import-directive-cpp.md)