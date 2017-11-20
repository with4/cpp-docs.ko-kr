---
title: 'Cenumerator:: Open | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: b22821a0-257a-4543-ad0c-2649d4ac092e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cf1205fce9466117a3374ebfd18e21cd034ae229
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cenumeratoropen"></a>CEnumerator::Open
지정 된 다음 호출 하 여 행 집합 열거자에 대 한 검색 하나는 열거자에 대 한 모니커를 바인딩합니다 [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/en-us/library/ms711200.aspx)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      HRESULT Open(   
   LPMONIKER pMoniker    
) throw( );  
HRESULT Open(   
   const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR    
) throw( );  
HRESULT Open(   
   const CEnumerator& enumerator    
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pMoniker`  
 [in] 열거자에 대 한 모니커에 대 한 포인터입니다.  
  
 *pClsid*  
 [in] 에 대 한 포인터는 **CLSID** 열거자입니다.  
  
 `enumerator`  
 [in] 열거자에 대 한 참조입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CEnumerator 클래스](../../data/oledb/cenumerator-class.md)