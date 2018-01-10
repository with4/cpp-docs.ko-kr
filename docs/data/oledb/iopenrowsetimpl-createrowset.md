---
title: 'Iopenrowsetimpl:: Createrowset | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- CreateRowset
dev_langs: C++
helpviewer_keywords: CreateRowset method
ms.assetid: 69041cf6-7a2f-4409-a26e-6e984c24986e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ada7e23a3ff48ea9b97263c8fa94a7970185f7a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="iopenrowsetimplcreaterowset"></a>IOpenRowsetImpl::CreateRowset
행 집합 개체를 만듭니다. 사용자가 직접 호출 되지 않습니다. 참조 [iopenrowset:: Openrowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) 에 *OLE DB 프로그래머 참조 합니다.*  
  
## <a name="syntax"></a>구문  
  
```  
  
      template <class   
      RowsetClass  
      >  
HRESULT CreateRowset(  
   IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `RowsetClass`  
 사용자의 행 집합 클래스를 나타내는 템플릿 클래스 멤버입니다. 일반적으로 마법사에서 생성 합니다.  
  
 `pRowsetObj`  
 [out] 행 집합 개체에 대 한 포인터입니다. 일반적으로이 매개 변수는 사용 되지 않지만 COM 개체를 전달 하기 전에 행 집합에서 더 많은 작업을 수행 해야 하는 경우 사용할 수 있습니다. 수명을 `pRowsetObj` 바인딩된 `ppRowset`합니다.  
  
 다른 매개 변수를 참조 하십시오. [iopenrowset:: Openrowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) 에 *OLE DB 프로그래머 참조 합니다.*  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IOpenRowsetImpl 클래스](../../data/oledb/iopenrowsetimpl-class.md)