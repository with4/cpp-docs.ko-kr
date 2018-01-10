---
title: 'Csession:: Open | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3aa0f6b694bc594ec00511ce39b7887bf26ecae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="csessionopen"></a>CSession::Open
데이터 원본 개체에 대 한 새 세션을 엽니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      HRESULT Open(  
   const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ds`  
 [in] 세션이 열어야 하는 데이터 원본입니다.  
  
 *pPropSet*  
 [in] 배열에 대 한 포인터 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 속성 및 값을 설정할 수를 포함 하는 구조체입니다. 참조 [속성 집합 및 속성 그룹](https://msdn.microsoft.com/en-us/library/ms713696.aspx) 에 *OLE DB Programmer's Reference* in the Windows SDK입니다.  
  
 `ulPropSets`  
 [in] 수가 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조체에 전달 된 *pPropSet* 인수입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여 데이터 원본 개체를 열어야 [cdatasource:: Open](../../data/oledb/cdatasource-open.md) 전달 하기 전에 `CSession::Open`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CSession 클래스](../../data/oledb/csession-class.md)