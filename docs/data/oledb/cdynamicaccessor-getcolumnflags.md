---
title: 'Cdynamicaccessor:: Getcolumnflags | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor.GetColumnFlags
- ATL::CDynamicAccessor::GetColumnFlags
- ATL.CDynamicAccessor.GetColumnFlags
- CDynamicAccessor::GetColumnFlags
- GetColumnFlags
dev_langs:
- C++
helpviewer_keywords:
- GetColumnFlags method
ms.assetid: b2ba2f3a-2c61-4a49-abfb-75823908ccf4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9cb4e439ab650793dcbafa79092d03b53271e45a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094698"
---
# <a name="cdynamicaccessorgetcolumnflags"></a>CDynamicAccessor::GetColumnFlags
열 특징을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```
bool GetColumnFlags(DBORDINAL nColumn,   
  DBCOLUMNFLAGS* pFlags) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nColumn`  
 [in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 0 값이 있는 경우 책갈피 열을 참조 합니다.  
  
 `pFlags`  
 [out] 열 특징을 설명 하는 비트 마스크에 대 한 포인터입니다. "DBCOLUMNFLAGS 열거 형식"을 참조 [icolumnsinfo:: Getcolumninfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="return-value"></a>반환 값  
 반환 **true** 열 특성을 성공적으로 검색 됩니다. 그렇지 않으면 **false**를 반환합니다.  
  
## <a name="remarks"></a>설명  
 열 번호 하나에서 5 만큼 오프셋 됩니다. 0 번 열은 특별 한 경우. 사용 가능한 경우 책갈피입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)