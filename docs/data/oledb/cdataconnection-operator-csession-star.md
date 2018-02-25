---
title: 'Cdataconnection:: Operator CSession * | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
dev_langs:
- C++
helpviewer_keywords:
- operator CSession*
- CSession* operator
ms.assetid: 0b0feede-5c3e-4835-be5b-03651597014d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 957e13346cb187540c21cbec71a642a917b69908
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnectionoperator-csession"></a>CDataConnection::operator CSession*
포함된 `CSession` 개체에 대한 포인터를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
operator const CSession*() throw();  
  
```  
  
## <a name="remarks"></a>설명  
 이 연산자는 `CSession` 포인터가 예상되는 위치에 `CDataConnection` 개체를 전달할 수 있게 해주는, 포함된 `CSession` 개체에 대한 포인터를 반환합니다.  
  
## <a name="example"></a>예  
 참조 [연산자 CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) 사용 예입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)