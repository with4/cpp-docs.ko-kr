---
title: 'Ierrorrecordsimpl:: Geterrordescriptionstring | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetErrorDescriptionString
- IErrorRecordsImpl.GetErrorDescriptionString
- IErrorRecordsImpl::GetErrorDescriptionString
dev_langs:
- C++
helpviewer_keywords:
- GetErrorDescriptionString method
ms.assetid: 8bc71c45-ca9f-4632-bb02-1aa9ed8086c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f0aea94e3a9f444b15b2f0d8f6ad14fe7543031e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101164"
---
# <a name="ierrorrecordsimplgeterrordescriptionstring"></a>IErrorRecordsImpl::GetErrorDescriptionString
오류 레코드에서 오류 설명 문자열을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `rCurError`  
 `ERRORINFO` 레코드에 **IErrorInfo** 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 오류를 설명 하는 문자열에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IErrorRecordsImpl 클래스](../../data/oledb/ierrorrecordsimpl-class.md)