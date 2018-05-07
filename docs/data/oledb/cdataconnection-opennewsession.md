---
title: 'Cdataconnection:: Opennewsession | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
dev_langs:
- C++
helpviewer_keywords:
- OpenNewSession method
ms.assetid: 0a70e573-9498-4ca7-b524-45666dc7b0a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f20f66ec6cc494c14e99c50de4824ba68d27264d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdataconnectionopennewsession"></a>CDataConnection::OpenNewSession
현재 연결 개체의 데이터 원본을 사용 하 여 새 세션을 엽니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT OpenNewSession(CSession & session) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `session`  
 [/ 출력] 새 세션 개체에 대 한 참조입니다.  
  
 **주의**  
 새 세션 그 부모 처럼 현재 연결 개체의 포함 된 데이터 원본 개체를 사용 하며 모든 데이터 소스와 동일한 정보를 액세스할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)