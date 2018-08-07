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
ms.openlocfilehash: 567a3387e79244443b784549d6223a14f78103ce
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464686"
---
# <a name="varianttattach"></a>_variant_t::Attach
**Microsoft 전용**  
  
 연결 된 `VARIANT` 개체를 **_variant_t** 개체.  
  
## <a name="syntax"></a>구문  
  
```  
void Attach(VARIANT& varSrc);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *varSrc*  
 A `VARIANT` 이 연결할 개체 **_variant_t** 개체입니다.  
  
## <a name="remarks"></a>설명  
 소유권을 `VARIANT` 캡슐화 하 여 그 합니다. 이 멤버 함수는 캡슐화 된 기존 릴리스 `VARIANT`, 다음 제공 된 복사 `VARIANT`를 설정 하 고 해당 `VARTYPE` 값을 vt_empty로 되도록 해당 리소스 에서만 해제할 수 있습니다는 **_variant_t** 소멸자입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [_variant_t 클래스](../cpp/variant-t-class.md)