---
title: 'Idbpropertiesimpl:: Setproperties | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl.SetProperties
- SetProperties
- IDBPropertiesImpl::SetProperties
dev_langs: C++
helpviewer_keywords: SetProperties method
ms.assetid: 2f9fc1de-7f35-4bca-bab3-7b427bf92c26
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d835810a2ca14c8e0631ed7dda8fcaddeb859d71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="idbpropertiesimplsetproperties"></a>IDBPropertiesImpl::SetProperties
열거자에 대 한 데이터 원본 개체에 대 한 데이터 원본 및 초기화 속성 그룹 또는 Initialization 속성 그룹의 속성을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      STDMETHOD(SetProperties)(   
   ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]    
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [idbproperties:: Setproperties](https://msdn.microsoft.com/en-us/library/ms723049.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드 설정에서 속성의 값 공급자가 초기화 하는 경우는 **DBPROPSET_DATASOURCE**, **DBPROPSET_DATASOURCEINFO**, **DBPROPSET_DBINIT** 속성 데이터 원본 개체에 대 한 그룹입니다. 공급자 초기화 되지 않은 경우 설정 **DBPROPSET_DBINIT** 만 속성을 그룹화 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IDBPropertiesImpl 클래스](../../data/oledb/idbpropertiesimpl-class.md)   
 [Idbpropertiesimpl:: Getproperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)