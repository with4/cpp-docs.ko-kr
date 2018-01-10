---
title: 'Cdbpropset:: Addproperty | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
dev_langs: C++
helpviewer_keywords: AddProperty method
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fa9c2d979bc98ebac543f0b17c7afdce2ab5f59b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropsetaddproperty"></a>CDBPropSet::AddProperty
속성은 속성 집합을 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      bool AddProperty(   
   DWORD dwPropertyID,   
   const VARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCSTR szValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCWSTR szValue,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   bool bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   BYTE bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   short nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   long nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   float fltValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   double dblValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   CY cyValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 *dwPropertyID*  
 [in] 추가할 속성의 ID입니다. 초기화 하는 데는 **dwPropertyID** 의 `DBPROP` 구조 속성 집합에 추가 합니다.  
  
 `var`  
 [in] 에 대 한 속성 값을 초기화 하는 데 사용 되는 variant는 `DBPROP` 구조 속성 집합에 추가 합니다.  
  
 `szValue`  
 [in] 에 대 한 속성 값을 초기화 하는 데 사용 하는 문자열은 `DBPROP` 구조 속성 집합에 추가 합니다.  
  
 `bValue`  
 [in] A **바이트** 또는 부울 값에 대 한 속성 값을 초기화 하는 데는 `DBPROP` 구조 속성 집합에 추가 합니다.  
  
 `nValue`  
 [in] 에 대 한 속성 값을 초기화 하는 데 사용 하는 정수 값의 `DBPROP` 구조 속성 집합에 추가 합니다.  
  
 *fltValue*  
 [in] 에 대 한 속성 값을 초기화 하는 데 사용 되는 부동 소수점 값의 `DBPROP` 구조 속성 집합에 추가 합니다.  
  
 `dblValue`  
 [in] 에 대 한 속성 값을 초기화 하는 데 사용 하는 두 자리 부동 소수점 값의 `DBPROP` 구조 속성 집합에 추가 합니다.  
  
 `cyValue`  
 [in] CY 통화 값에 대 한 속성 값을 초기화 하는 데는 `DBPROP` 구조 속성 집합에 추가 합니다.  
  
## <a name="return-value"></a>반환 값  
 **true 이면** 경우 속성이 추가 되었습니다. 그렇지 않으면 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDBPropSet 클래스](../../data/oledb/cdbpropset-class.md)   
 [DBPROP 구조](https://msdn.microsoft.com/en-us/library/ms717970.aspx)