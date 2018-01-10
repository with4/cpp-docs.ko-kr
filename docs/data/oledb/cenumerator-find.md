---
title: 'Cenumerator:: Find | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
dev_langs: C++
helpviewer_keywords: Find method
ms.assetid: 69a153af-d6c3-40fd-9018-27c7d2f344c6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1d7c2deef184ef9e56dffcfba52ba2cbb2947519
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cenumeratorfind"></a>CEnumerator::Find
사용 가능한 공급자 중에서 지정된 된 이름을 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      bool Find(   
   TCHAR* szSearchName    
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 *szSearchName*  
 [in] 이름에 대 한 검색입니다.  
  
## <a name="return-value"></a>반환 값  
 **true 이면** 경우에서 이름을 찾을 수 있습니다. 그렇지 않으면 **false**합니다.  
  
## <a name="remarks"></a>설명  
 이 이름이 매핑되는 **SOURCES_NAME** 의 멤버는 [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CEnumerator 클래스](../../data/oledb/cenumerator-class.md)