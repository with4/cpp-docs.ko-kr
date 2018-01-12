---
title: 'Cdynamicaccessor:: Getordinal | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor.GetOrdinal
- ATL::CDynamicAccessor::GetOrdinal
- CDynamicAccessor::GetOrdinal
- ATL.CDynamicAccessor.GetOrdinal
- GetOrdinal
dev_langs: C++
helpviewer_keywords: GetOrdinal method
ms.assetid: 2095b71c-a7a4-4034-89a1-77a78cb9633f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b86ce9f5b27e7dc51cbebdbbd24b90dd9effa5fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessorgetordinal"></a>CDynamicAccessor::GetOrdinal
열 이름이 지정 된 열 번호를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      bool GetOrdinal(  
   const CHAR* pColumnName,  
   DBORDINAL* pOrdinal   
) const throw( );  
bool GetOrdinal(  
   const WCHAR* pColumnName,  
   DBORDINAL* pOrdinal   
) const throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pColumnName`  
 [in] 열 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 *pOrdinal*  
 [out] 열 번호에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 **true** 경우 지정된 된 이름 가진 열을 찾을 수 있습니다. 그렇지 않으면이 함수가 반환 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)