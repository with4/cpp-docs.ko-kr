---
title: 'Cdataconnection:: Operator CDataSource&amp; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
dev_langs: C++
helpviewer_keywords:
- CDataSource& operator
- operator & (CDataSource)
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5cd6c1821f49ba56b8d6ca27932b6cd7f0e17bf6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdataconnectionoperator-cdatasourceamp"></a>Cdataconnection:: Operator CDataSource&amp;
포함 된에 대 한 참조를 반환 `CDataSource` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
operator const CDataSource&() throw( );  
  
```  
  
## <a name="remarks"></a>설명  
 이 연산자는 포함 된에 대 한 참조를 반환 합니다. `CDataSource` 개체를 전달할 수 있습니다는 `CDataConnection` 개체 위치는 `CDataSource` 참조가 필요 합니다.  
  
## <a name="example"></a>예  
 함수가 (같은 `func` 아래)를 사용 하는 `CDataSource` 참조, 있습니다 사용할 수 있습니다 **CDataSource &** 전달 하는 `CDataConnection` 개체를 대신 합니다.  
  
 [!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)