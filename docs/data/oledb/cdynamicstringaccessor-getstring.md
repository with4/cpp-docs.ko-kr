---
title: 'Cdynamicstringaccessor:: Getstring | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
dev_langs:
- C++
helpviewer_keywords:
- GetString method
ms.assetid: 4af27f27-7589-49f5-93d8-6ef05c023c8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cc23fe73eb0d804d0b53950885b1b83aba58ff91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicstringaccessorgetstring"></a>CDynamicStringAccessor::GetString
지정된 열 데이터를 문자열로 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      BaseType* GetString(DBORDINAL nColumn) const throw();  

BaseType* GetString(const CHAR* pColumnName) const throw();  

BaseType* GetString(const WCHAR* pColumnName) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nColumn`  
 [in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 0 값이 있는 경우 책갈피 열을 참조 합니다.  
  
 `pColumnName`  
 [in] 열 이름이 포함 된 문자열에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 문자열 값에 대 한 포인터는 지정된 된 열에서 검색 합니다. 형식의 값은 ***BaseType***, 될 **CHAR** 또는 **WCHAR** _UNICODE가 정의 되었는지에 따라 합니다. 지정된 된 열을 찾을 수 없는 경우 NULL을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 두 번째는 ANSI 문자열로 폼은 열 이름을 재정의 합니다. 세 번째 폼은 열 이름을 유니코드 문자열로 재정의 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicStringAccessor Class](../../data/oledb/cdynamicstringaccessor-class.md)