---
title: 'Cutlprops:: Getpropvalue | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
dev_langs:
- C++
helpviewer_keywords:
- GetPropValue method
ms.assetid: 9a3fbadb-7814-48f7-96a4-b960fc4ecf2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 00f56c317f9325fa51f7165fc3872b1e4ca6e9da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cutlpropsgetpropvalue"></a>CUtlProps::GetPropValue
속성 집합에서 속성을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pguidPropSet`  
 [in] 속성 집합에 대 한 GUID입니다.  
  
 `dwPropId`  
 [in] 속성 인덱스입니다.  
  
 `pvValue`  
 [out] 새 속성 값을 포함 하는 variant에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `Failure` 실패 시 및 `S_OK` 성공 하는 경우.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [CUtlProps 클래스](../../data/oledb/cutlprops-class.md)