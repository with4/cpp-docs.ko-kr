---
title: 'Caccessorbase:: Releaseaccessors | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CAccessorBase::ReleaseAccessors
- CAccessorBase.ReleaseAccessors
- ReleaseAccessors
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAccessors method
ms.assetid: f08bc88e-0552-4a9c-9c65-b4061094649a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c73035e27b1f896891630cd9b4d9a135b3c4758
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="caccessorbasereleaseaccessors"></a>CAccessorBase::ReleaseAccessors
클래스로 만든 접근자를 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT ReleaseAccessors(IUnknown* pUnk);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *pUnk*  
 [in] 에 대 한 포인터는 **IUnknown** 접근자 생성 된 COM 개체에 대 한 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 호출 [caccessorrowset:: Close](../../data/oledb/caccessorrowset-close.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CAccessorBase 클래스](../../data/oledb/caccessorbase-class.md)