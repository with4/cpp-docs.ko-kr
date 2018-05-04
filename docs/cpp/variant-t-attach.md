---
title: _variant_t::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93c4ec0b4d25f1ca0ec03d9aae1dd9e1c16b79a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="varianttattach"></a>_variant_t::Attach
**Microsoft 전용**  
  
 연결 된 **VARIANT** 개체는 `_variant_t` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *varSrc*  
 A **VARIANT** 개체를이 연결 `_variant_t` 개체입니다.  
  
## <a name="remarks"></a>설명  
 소유권은 **VARIANT** 캡슐화 하 여 그 합니다. 이 멤버 함수를 캡슐화 된 기존 해제 **VARIANT**, 다음 제공 된 복사 **VARIANT**, 설정 및 해당 **VARTYPE** 를 `VT_EMPTY` 되도록 해당 리소스에서 해제 될 수는 `_variant_t` 소멸자입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_variant_t 클래스](../cpp/variant-t-class.md)