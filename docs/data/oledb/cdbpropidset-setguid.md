---
title: 'Cdbpropidset:: Setguid | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs: C++
helpviewer_keywords: SetGUID method
ms.assetid: 8dd0f3bf-1490-4d53-9063-322b8d821bbe
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aa70e704cd8e132404442ef390ea5582155a76e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropidsetsetguid"></a>CDBPropIDSet::SetGUID
GUID 필드 설정는 **DBPROPIDSET** 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guid`  
 [in] 설정 하는 데 GUID는 **guidPropertySet** 필드는 [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) 구조입니다.  
  
## <a name="remarks"></a>설명  
 이 필드를 설정할 수 있습니다는 [생성자](../../data/oledb/cdbpropidset-cdbpropidset.md) 도 합니다. 이 클래스에 대 한 기본 생성자를 사용 하는 경우이 함수를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDBPropIDSet 클래스](../../data/oledb/cdbpropidset-class.md)