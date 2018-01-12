---
title: 'Crestrictions:: Open | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: 0aff0cc3-543a-47d2-8d6b-ebb36926b6db
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bbb0b175a6fa5a6cf93b4fe107884d5bb84f2487
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="crestrictionsopen"></a>CRestrictions::Open
결과 사용자가 제공한 제한에 따라 집합을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `session`  
 [in] 데이터 원본에 연결 하는 데 사용 되는 기존 세션 개체를 지정 합니다.  
  
 *lpszParam*  
 [in] 스키마 행 집합에 대 한 제한을 지정 합니다.  
  
 `bBind`  
 [in] 열 지도 자동으로 바인딩할 것인지를 지정 합니다. 기본값은 **true**, 자동으로 바인딩할 열 지도 이르게 됩니다. 설정 `bBind` 를 **false** 수동으로 바인딩할 수 있도록 열 맵의 자동 바인딩 방지 합니다. (수동 바인딩은 OLAP 사용자에 게 특히 중요 합니다.)  
  
## <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
## <a name="remarks"></a>설명  
 스키마 행 집합에서 7 제한의 최대값을 지정할 수 있습니다.  
  
 참조 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 각 스키마 행 집합에 정의 된 제한에 대 한 정보에 대 한 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbsch.h  
  
## <a name="see-also"></a>참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)   
 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)