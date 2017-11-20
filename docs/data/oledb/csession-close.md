---
title: 'Csession:: Close | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSession::Close
- ATL.CSession.Close
- CSession.Close
- ATL::CSession::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: dc36c4c0-e588-4c0b-91d1-fc7dc5c8e7f4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 70016d94916bbd3479e0daa7d42c7a1f4a8785c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="csessionclose"></a>CSession::Close
열려 있는 세션을 닫을 [csession:: Open](../../data/oledb/csession-open.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
void Close( ) throw( );  
  
```  
  
## <a name="remarks"></a>설명  
 릴리스는 **m_spOpenRowset** 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CSession 클래스](../../data/oledb/csession-class.md)