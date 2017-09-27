---
title: _variant_t::Detach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
dev_langs:
- C++
helpviewer_keywords:
- VARIANT object, detatch
- Detach method
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 402d8bfeb6aea45460124bdeaaa8b3ee485df622
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="varianttdetach"></a>_variant_t::Detach
**Microsoft 전용**  
  
 캡슐화 된 분리 **VARIANT** 이 개체 `_variant_t` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
VARIANT Detach( );  
  
```  
  
## <a name="return-value"></a>반환 값  
 캡슐화 된 **VARIANT**합니다.  
  
## <a name="remarks"></a>설명  
 추출 하 고 반환 캡슐화 된 **VARIANT**,이 지우고 `_variant_t` 삭제 하지 않고 개체입니다. 이 멤버 함수를 제거는 **VARIANT** 캡슐화 및 집합에서의 **VARTYPE** 이 `_variant_t` 개체 `VT_EMPTY`합니다. 반환 된 해제 하기 위해 사용자가 결정 **VARIANT** 호출 하 여는 [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835) 함수입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_variant_t 클래스](../cpp/variant-t-class.md)
