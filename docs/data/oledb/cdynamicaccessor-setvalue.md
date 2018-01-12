---
title: 'Cdynamicaccessor:: Setvalue | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
dev_langs: C++
helpviewer_keywords: SetValue method
ms.assetid: ecc18850-96e5-4845-abe5-ab34ad467238
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bdd334f916257d3688658e941522b6cc20b12b40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessorsetvalue"></a>CDynamicAccessor::SetValue
지정 된 열에 데이터를 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      template < class ctype >    
bool SetValue(   
   DBORDINAL nColumn,   
   const ctype& data    
) throw( );  
template < class ctype >    
bool SetValue(   
   const CHAR * pColumnName,   
   const ctype& data    
) throw( );  
template <class ctype>   
bool SetValue(  
   const WCHAR *pColumnName,  
   const ctype& data   
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ctype`  
 [in] 문자열 형식 제외한 모든 데이터 형식을 처리 하는 템플릿 매개 변수 (**CHAR\***, **WCHAR\***), 특수 한 처리 해야 합니다. `GetValue`지정한 것 여기에 따라 적절 한 데이터 형식을 사용 합니다.  
  
 `pColumnName`  
 [in] 열 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `data`  
 [in] 데이터를 포함 하는 메모리 포인터입니다.  
  
 `nColumn`  
 [in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 0 값이 있는 경우 책갈피 열을 참조 합니다.  
  
## <a name="return-value"></a>반환 값  
 문자열 데이터를 설정 하려는 경우 템플릿이 아닌 버전의 사용 `GetValue`합니다. 이 메서드의 템플릿이 아닌 버전은 반환 **void\***, 지정된 된 열 데이터를 포함 하는 버퍼의 일부를 가리키는 합니다. 반환 **NULL** 열을 찾을 수 없는 경우.  
  
 다른 모든 데이터 형식에 대 한 템플릿 버전을 사용 하는 `GetValue`합니다. 템플릿 기반 버전에서는 반환 **true** 성공 또는 **false** 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)