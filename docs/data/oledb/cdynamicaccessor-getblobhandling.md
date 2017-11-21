---
title: 'Cdynamicaccessor:: Getblobhandling | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicAccessor.GetBlobHandling
- CDynamicAccessor::GetBlobHandling
- ATL::CDynamicAccessor::GetBlobHandling
- GetBlobHandling
- CDynamicAccessor.GetBlobHandling
dev_langs: C++
helpviewer_keywords: GetBlobHandling method
ms.assetid: bbc6dda6-e132-42a3-980d-24e455cbe456
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b9bac84019f408c7a68cf6afbffe94572be44c46
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicaccessorgetblobhandling"></a>CDynamicAccessor::GetBlobHandling
현재 행에 대 한 값을 처리 하는 BLOB를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
const DBBLOBHANDLINGENUM GetBlobHandling( ) const;  
  
```  
  
## <a name="remarks"></a>설명  
 반환 값을 처리 하는 BLOB `eBlobHandling` 의해 설정 [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)