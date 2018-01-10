---
title: 'Cdynamicparameteraccessor:: Setparamstring | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
dev_langs: C++
helpviewer_keywords: SetParamString method
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75d6e9887b609349a092bb67e55508ca1429387b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorsetparamstring"></a>CDynamicParameterAccessor::SetParamString
버퍼에 저장된 지정된 매개 변수의 문자열 데이터를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      bool SetParamString(   
   DBORDINAL nParam,   
   const CHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
bool SetParamString(   
   DBORDINAL nParam,   
   const WCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nParam`  
 [in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예에 대 한 합니다.  
  
 `pString`  
 [in] ANSI에 대 한 포인터 (**CHAR**) 또는 유니코드 (**WCHAR**) 문자열 데이터의 지정된 된 매개 변수입니다. 참조 `DBSTATUS` oledb.h에서 합니다.  
  
 *status*  
 [in] `DBSTATUS` 지정된 된 매개 변수의 상태입니다. 에 대 한 내용은 `DBSTATUS` 값, 참조 [상태](https://msdn.microsoft.com/en-us/library/ms722617.aspx) 에 *OLE DB Programmer's Reference*, 검색 또는 `DBSTATUS` oledb.h에서 합니다.  
  
## <a name="remarks"></a>설명  
 반환 **true** 성공 또는 **false** 실패 합니다.  
  
 `SetParamString`에 대 한 지정 된 최대 크기 보다 큰 문자열을 설정 하려고 하면 실패 합니다 `pString`합니다.  
  
 사용 하 여 `SetParamString` 버퍼에 문자열 매개 변수 데이터를 설정할 수 있습니다. 사용 하 여 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 버퍼에 문자열이 아닌 매개 변수 데이터를 설정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)