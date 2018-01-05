---
title: BEGIN_ACCESSOR_MAP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_ACCESSOR_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_ACCESSOR_MAP macro
ms.assetid: e6d6e3a4-62fa-4e49-8c53-caf8c9d20091
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1ff08fd95e9e84d47562a5fafb8bf7be04e41ed6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="beginaccessormap"></a>BEGIN_ACCESSOR_MAP
접근자 맵 항목의 시작을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
BEGIN_ACCESSOR_MAP(  
x  
,   
num  
 )  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 사용자 레코드 클래스의 이름입니다.  
  
 *num*  
 [in] 이 접근자 맵에 있는 접근자 수입니다.  
  
## <a name="remarks"></a>설명  
 행 집합에 여러 접근자가 있는 경우 시작 부분에 `BEGIN_ACCESSOR_MAP` 을 지정하고 각 접근자에 `BEGIN_ACCESSOR` 매크로를 사용해야 합니다. `BEGIN_ACCESSOR` 매크로는 `END_ACCESSOR` 매크로로 완료됩니다. 접근자 맵은 `END_ACCESSOR_MAP` 매크로로 완료됩니다.  
  
 사용자 레코드에 접근자가 하나만 있는 경우 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)매크로를 사용합니다.  
  
## <a name="example"></a>예  

 ```cpp  
class CArtistsAccessor
{
public:
// Data Elements
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];
   short m_nAge;

// Output binding map
BEGIN_ACCESSOR_MAP(CArtistsAccessor, 2)
   BEGIN_ACCESSOR(0, true)
      COLUMN_ENTRY(1, m_szFirstName)
      COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false) // Not an auto accessor
      COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsAccessor, L" \
   SELECT \
      FirstName, \
      LastName, \
      Age \
      FROM Artists")
};
 ```

  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)