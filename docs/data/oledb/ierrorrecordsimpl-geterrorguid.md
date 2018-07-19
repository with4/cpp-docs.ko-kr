---
title: 'Ierrorrecordsimpl:: Geterrorguid | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetErrorGUID
- IErrorRecordsImpl.GetErrorGUID
- IErrorRecordsImpl::GetErrorGUID
dev_langs:
- C++
helpviewer_keywords:
- GetErrorGUID method
ms.assetid: 42c00755-50e5-401a-8246-adef9de5ced2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a17529b9132a322cf1610baa1463d921c313e118
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100345"
---
# <a name="ierrorrecordsimplgeterrorguid"></a>IErrorRecordsImpl::GetErrorGUID
오류 레코드에서 오류를 GUID를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      REFGUID GetErrorGUID(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `rCurError`  
 `ERRORINFO` 레코드에 **IErrorInfo** 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 오류에 대 한 GUID에 대 한 참조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IErrorRecordsImpl 클래스](../../data/oledb/ierrorrecordsimpl-class.md)