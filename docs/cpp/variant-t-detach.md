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
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 577b4874dd6d89c0c6c60b1a7981e74944e77ba8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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