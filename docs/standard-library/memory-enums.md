---
title: "&lt;memory&gt; 열거형 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9c3440495d77b788658cffefc917d9960ca1f833
ms.lasthandoff: 02/24/2017

---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; 열거형
||  
|-|  
|[pointer_safety 열거형](#pointer_safety_enumeration)|  
  
##  <a name="a-namepointersafetyenumerationa--pointersafety-enumeration"></a><a name="pointer_safety_enumeration"></a>  pointer_safety 열거형  
 `get_pointer_safety`에서 반환할 수 있는 값의 열거형입니다.  
  
class pointer_safety { relaxed, preferred, strict };  
  
### <a name="remarks"></a>설명  
 범위 `enum`은 `get_pointer_safety``()`에서 반환할 수 있는 값을 정의합니다.  
  
 `relaxed` - 안전하게 파생되지 않은 포인터(선언되거나 할당된 개체에 대한 포인터)를 안전하게 파생된 포인터와 동일하게 처리합니다.  
  
 `preferred` - 이전 설명과 같지만 안전하게 파생되지 않은 포인터를 역참조해서는 안 됩니다.  
  
 `strict` - 안전하게 파생되지 않은 포인터를 안전하게 파생된 포인터와 다르게 처리할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<memory>](../standard-library/memory.md)




