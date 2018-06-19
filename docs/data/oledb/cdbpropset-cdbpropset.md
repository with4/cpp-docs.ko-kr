---
title: 'Cdbpropset:: Cdbpropset | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropSet class, constructor
ms.assetid: 02ae5d9e-c067-47ca-8111-a03e86b5626b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 58c3639d6c849a4b57ba1b0a75a7840def977556
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090476"
---
# <a name="cdbpropsetcdbpropset"></a>CDBPropSet::CDBPropSet
생성자입니다. 초기화는 **rgProperties**, **cProperties**, 및 **guidPropertySet** 의 필드는 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      CDBPropSet(const GUID& guid);  

CDBPropSet(const CDBPropSet& propset);  

CDBPropSet();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guid`  
 [in] GUID를 초기화 하는 데 사용 된 **guidPropertySet** 필드입니다.  
  
 *propset*  
 [in] 복사 생성을 위한 다른 `CDBPropSet` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDBPropSet 클래스](../../data/oledb/cdbpropset-class.md)   
 [CDBPropSet::SetGUID](../../data/oledb/cdbpropset-setguid.md)   
 [DBPROP 구조](https://msdn.microsoft.com/en-us/library/ms717970.aspx)