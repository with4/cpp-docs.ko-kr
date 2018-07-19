---
title: 'Cdataconnection:: Operator bool (OLE DB) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- operator bool
ms.assetid: e0791faf-2ed2-4dbb-9e68-3b9b5da2b7a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1f466085f1003ca14f9df6db648ba7a3f833b3b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093443"
---
# <a name="cdataconnectionoperator-bool-ole-db"></a>CDataConnection::operator bool(OLE DB)
현재 세션이 열려 있는지 여부를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
operator bool() throw();  
  
```  
  
## <a name="remarks"></a>설명  
 반환 된 `bool` (c + + 데이터 형식) 값입니다. **true** 열려 있습니다; 현재 세션은 **false** 현재 세션이 닫히면 것을 의미 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator BOOL](../../data/oledb/cdataconnection-operator-bool.md)