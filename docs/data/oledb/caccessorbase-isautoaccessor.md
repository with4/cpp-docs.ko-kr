---
title: 'Caccessorbase:: Isautoaccessor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
dev_langs: C++
helpviewer_keywords: IsAutoAccessor method
ms.assetid: c330da15-2947-4050-ad00-8f776adc58fb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 677eb2d2ca8d719598090e1753275e2429706b83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="caccessorbaseisautoaccessor"></a>CAccessorBase::IsAutoAccessor
이동 작업 중 접근자에 대 한 데이터를 자동으로 검색 하는 경우 true를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      bool IsAutoAccessor(  
   ULONG nAccessor   
) const;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nAccessor`  
 [in] 접근자에 대한 0 오프셋의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 **true** 접근자가 자동 하는 경우. 그렇지 않으면 **false**를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CAccessorBase 클래스](../../data/oledb/caccessorbase-class.md)