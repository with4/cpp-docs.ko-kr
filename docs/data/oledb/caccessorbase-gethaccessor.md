---
title: 'Caccessorbase:: Gethaccessor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
dev_langs:
- C++
helpviewer_keywords:
- GetHAccessor method
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2bacc7f24d112fc6714200c6347e66bb66866831
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088787"
---
# <a name="caccessorbasegethaccessor"></a>CAccessorBase::GetHAccessor
지정된 접근자의 접근자 핸들을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      HACCESSOR GetHAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nAccessor`  
 [in] 접근자에 대한 0 오프셋의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 접근자 핸들입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CAccessorBase 클래스](../../data/oledb/caccessorbase-class.md)