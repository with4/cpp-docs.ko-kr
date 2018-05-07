---
title: 'Csession:: Close | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession::Close
- ATL.CSession.Close
- CSession.Close
- ATL::CSession::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: dc36c4c0-e588-4c0b-91d1-fc7dc5c8e7f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c8c40ba6b291ed17f4af772cd438756ea868f174
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="csessionclose"></a>CSession::Close
열려 있는 세션을 닫을 [csession:: Open](../../data/oledb/csession-open.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
void Close() throw();  
  
```  
  
## <a name="remarks"></a>설명  
 릴리스는 **m_spOpenRowset** 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CSession 클래스](../../data/oledb/csession-class.md)