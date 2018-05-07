---
title: 'Cdynamicaccessor:: Getlength | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
dev_langs:
- C++
helpviewer_keywords:
- GetLength method
ms.assetid: 3ae8983b-b267-4cf9-bfc0-3e191f79e646
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cc7203f030fc3a9ca00839bc9955c85eaa770935
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorgetlength"></a>CDynamicAccessor::GetLength
지정 된 열의 길이 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```
bool GetLength(DBORDINAL nColumn,   
  DBLENGTH* pLength) const throw();  

bool GetLength(const CHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  

bool GetLength(const WCHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nColumn`  
 [in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 0 값이 있는 경우 책갈피 열을 참조 합니다.  
  
 `pColumnName`  
 [in] 열 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `pLength`  
 [out] 바이트의 열 길이 포함 하는 정수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 **true** 지정된 된 열이 있으면 합니다. 그렇지 않으면이 함수가 반환 **false**합니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 재정의 열 번호를 사용 하 고 두 번째 및 세 번째 재정의 ANSI 또는 유니코드 형식으로 각각 열 이름의 수행 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetLength](../../data/oledb/cdynamicaccessor-setlength.md)