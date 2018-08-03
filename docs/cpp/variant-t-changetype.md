---
title: _variant_t::ChangeType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs:
- C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f3790f4cb357ed830ba2c61b3c2906356dc64da
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465590"
---
# <a name="varianttchangetype"></a>_variant_t::ChangeType
**Microsoft 전용**  
  
 형식을 변경 합니다 `_variant_t` 표시 된 개체 `VARTYPE`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *vartype*  
 합니다 `VARTYPE` 이 `_variant_t` 개체입니다.  
  
 *pSrc*  
 변환할 `_variant_t` 개체의 포인터입니다. 이 값이 NULL 인 경우 변환 위치에서 수행 됩니다.  
  
## <a name="remarks"></a>설명  
 이 멤버 함수는 변환 된 `_variant_t` 개체로 표시 된 `VARTYPE`합니다. 하는 경우 *pSrc* 가 null 인 경우 변환은 이렇게 적용이 고 그렇지 `_variant_t` 개체에서 복사 됩니다 *pSrc* 변환한 후 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [_variant_t 클래스](../cpp/variant-t-class.md)