---
title: 'Cdataconnection:: Operator CDataSource * | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
dev_langs:
- C++
helpviewer_keywords:
- CDataSource* operator
- operator * (CDataSource)
ms.assetid: 9118e324-e68d-45c5-a791-03f041d420ed
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 60eba58d4a3884b191afdca1da0934453a303d8c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnectionoperator-cdatasource"></a>CDataConnection::operator CDataSource*
포함된 `CDataSource` 개체에 대한 포인터를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
operator const CDataSource*() throw();  
  
```  
  
## <a name="remarks"></a>설명  
 이 연산자는 `CDataSource` 포인터가 예상되는 위치에 `CDataConnection` 개체를 전달할 수 있게 해주는, 포함된 `CDataSource` 개체에 대한 포인터를 반환합니다.  
  
 참조 [operator CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) 사용 예입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)