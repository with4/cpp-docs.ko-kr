---
title: 'Cdataconnection:: Operator CSession&amp; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
dev_langs:
- C++
helpviewer_keywords:
- operator CSession&
- CSession& operator
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d46aeb352016c41dddaee972d438be8c28e22a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095423"
---
# <a name="cdataconnectionoperator-csessionamp"></a>Cdataconnection:: Operator CSession&amp;
포함 된에 대 한 참조를 반환 `CSession` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
operator const CSession&();  
  
```  
  
## <a name="remarks"></a>설명  
 이 연산자는 포함 된에 대 한 참조를 반환 합니다. `CSession` 개체를 전달할 수 있습니다는 `CDataConnection` 개체 위치는 `CSession` 참조가 필요 합니다.  
  
## <a name="example"></a>예제  
 함수가 (같은 `func` 아래)를 사용 하는 `CSession` 참조, 있습니다 사용할 수 있습니다 **CSession &** 전달 하는 `CDataConnection` 개체를 대신 합니다.  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession*](../../data/oledb/cdataconnection-operator-csession-star.md)