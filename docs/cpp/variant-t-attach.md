---
title: _variant_t::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 33e21d3bea71c80b8b60df222682fda560fbce9c
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

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
