---
title: 'Cxmlaccessor:: Getxmlcolumndata | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CXMLAccessor.GetXMLColumnData
- CXMLAccessor::GetXMLColumnData
- CXMLAccessor.GetXMLColumnData
- ATL::CXMLAccessor::GetXMLColumnData
- GetXMLColumnData
dev_langs:
- C++
helpviewer_keywords:
- GetXMLColumnData method
ms.assetid: 719e8efe-8758-4af7-a855-0e44ea196546
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0e9a11434be63b75eef5ac0aaed729b7a8c2f0b7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="cxmlaccessorgetxmlcolumndata"></a>CXMLAccessor::GetXMLColumnData
열에서 XML 형식의 문자열 데이터로 테이블의 열 형식 정보를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetXMLColumnData(CSimpleStringW& strOutput) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `strOutput`  
 [out] 검색할 열 형식 정보를 포함 하는 문자열 버퍼에 대 한 참조입니다. 문자열의 데이터 저장소의 열 이름과 일치 하는 XML 태그 이름으로 지정 합니다.  
  
## <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
## <a name="remarks"></a>설명  
 다음 열 형식 정보를 XML 형식 지정 방법을 보여 줍니다. `type` 열의 데이터 형식을 지정합니다. 데이터 형식은 OLE DB 데이터 형식 액세스 중인 데이터베이스의 인수와 하지 기반는 note 합니다.  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CXMLAccessor 클래스](../../data/oledb/cxmlaccessor-class.md)