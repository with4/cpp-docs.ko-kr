---
title: 'Cdynamicaccessor:: Getcolumninfo | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetColumnInfo
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- GetColumnInfo method
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9f311e9fc5330a68edba4fd5029e97b75033406
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorgetcolumninfo"></a>CDynamicAccessor::GetColumnInfo
대부분의 소비자에 필요한 열 메타 데이터를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetColumnInfo(IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRowset`  
 [in] 에 대 한 포인터는 [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) 인터페이스입니다.  
  
 *pColumns*  
 [out] 행 집합의 열 수를 반환할 메모리에 대 한 포인터 있는 경우이 수는 책갈피 열을 포함 됩니다.  
  
 *ppColumnInfo*  
 [out] 배열을 반환할 메모리에 대 한 포인터 **DBCOLUMNINFO** 구조입니다. "DBCOLUMNINFO 구조"를 참조 하십시오. [icolumnsinfo:: Getcolumninfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 `ppStringsBuffer`  
 [out] 모든 문자열 값에 대 한 저장소에 대 한 포인터를 반환할 메모리에 대 한 포인터 (이름이 사용 범위에 속해 있거나 *columnid* 또는 *pwszName*) 단일 할당 블록 내에서.  
  
## <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
## <a name="remarks"></a>설명  
 참조 [icolumnsinfo:: Getcolumninfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) 에 *OLE DB Programmer's Reference* 데이터 형식에 대 한 내용은 **DBORDINAL**, **DBCOLUMNINFO**, 및 **OLECHAR**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)