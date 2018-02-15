---
title: 'Cdynamicaccessor:: Getvalue | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
dev_langs:
- C++
helpviewer_keywords:
- GetValue method
ms.assetid: 553f44af-68bc-4cb6-8774-e0940003fa90
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1602b784db2f6eac0984ce1fca3fb8d1276b0666
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicaccessorgetvalue"></a>CDynamicAccessor::GetValue
지정된 된 열에 대 한 데이터를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
void* GetValue(DBORDINAL nColumn) const throw();  

void* GetValue(const CHAR* pColumnName) const throw();  

void* GetValue(const WCHAR* pColumnName) const throw();  

template < class ctype >
bool GetValue(DBORDINAL nColumn, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const CHAR* pColumnName, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const WCHAR* pColumnName, ctype* pData) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ctype`  
 [in] 문자열 형식 제외한 모든 데이터 형식을 처리 하는 템플릿 매개 변수 (**CHAR\***, **WCHAR\***), 특수 한 처리 해야 합니다. `GetValue` 지정한 것 여기에 따라 적절 한 데이터 형식을 사용 합니다.  
  
 `nColumn`  
 [in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 0 값이 있는 경우 책갈피 열을 참조 합니다.  
  
 `pColumnName`  
 [in] 열 이름입니다.  
  
 `pData`  
 [out] 지정 된 열의 내용에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 문자열 데이터를 전달 하려는 경우 템플릿이 아닌 버전의 사용 `GetValue`합니다. 이 메서드의 템플릿이 아닌 버전은 반환 **void\***, 지정된 된 열 데이터를 포함 하는 버퍼의 일부를 가리키는 합니다. 반환 **NULL** 열을 찾을 수 없는 경우.  
  
 다른 모든 데이터 형식에 대 한 템플릿 버전을 사용 하는 `GetValue`합니다. 템플릿 기반 버전에서는 반환 **true** 성공 또는 **false** 실패 합니다.  
  
## <a name="remarks"></a>설명  
 템플릿이 아닌 버전을 사용 하 여 문자열 및 다른 데이터 형식이 포함 된 열에 대 한 템플릿 버전을 포함 하는 열을 반환 합니다.  
  
 디버그 모드에서 하면 얻을 수 있습니다는 어설션을 크기 `pData` 가리키는 열의 크기와 같지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)