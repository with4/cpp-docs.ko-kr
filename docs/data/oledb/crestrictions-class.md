---
title: CRestrictions 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
dev_langs:
- C++
helpviewer_keywords:
- CRestrictions class
- Open method
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aa95eb630fac2fe30014e378cc79bdbac285dbdb
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233505"
---
# <a name="crestrictions-class"></a>CRestrictions 클래스
스키마 행 집합에 대 한 제한을 지정할 수 있는 제네릭 클래스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T, short nRestrictions, const GUID* pguid>  
class CRestrictions : 
        public CSchemaRowset <T, nRestrictions>  
```  
  
#### <a name="parameters"></a>매개 변수  
 *T*  
 접근자에 사용 되는 클래스입니다.  
  
 *nRestrictions*  
 스키마 행 집합에 대 한 제한 열의 수입니다.  
  
 *pguid*  
 스키마에 대 한 GUID에 대 한 포인터입니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldbsch.h 
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[열기](#open)|결과 사용자가 제공한 제한 사항에 따라 집합을 반환 합니다.|   

## <a name="open"></a> Crestrictions:: Open
결과 사용자가 제공한 제한 사항에 따라 집합을 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *세션*  
 [in] 데이터 원본에 연결 하는 데 기존 세션 개체를 지정 합니다.  
  
 *lpszParam*  
 [in] 스키마 행 집합에는 제한을 지정합니다.  
  
 *bBind*  
 [in] 열 지도 자동으로 바인딩할 지 여부를 지정 합니다. 기본값은 **true**를 자동으로 바인딩할 열 지도 이르게 합니다. 설정 *bBind* 하 **false** 수동으로 바인딩할 수 있도록 열 맵의 자동 바인딩 방지 합니다. (수동 바인딩으로 OLAP 사용자에 게 특히 관심입니다.)  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>설명  
 스키마 행 집합에서 최대 7 개의 제한 지정할 수 있습니다.  
  
 참조 [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) 각 스키마 행 집합에서 정의 된 제한에 대 한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)    
 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)