---
title: 'Cdataconnection:: Cdataconnection | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class, constructor
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 267341f88886f3ff94a6b828034e8acbaa2dc0c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093326"
---
# <a name="cdataconnectioncdataconnection"></a>CDataConnection::CDataConnection
인스턴스화하고 초기화는 `CDataConnection` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      CDataConnection();   

CDataConnection(const CDataConnection &ds);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ds`  
 [in] 기존 데이터 연결에 대 한 참조입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 재정의 새로 만들고 `CDataConnection` 기본 설정으로는 개체입니다.  
  
 두 번째 재정의에서는 새 `CDataConnection` 설정을 지정 하는 데이터 연결 개체에 해당 하는 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)