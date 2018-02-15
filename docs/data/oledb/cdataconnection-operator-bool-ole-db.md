---
title: 'Cdataconnection:: Operator bool (OLE DB) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5a3d8317df5d7ed4d034b2d16b9d282aab08f848
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
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