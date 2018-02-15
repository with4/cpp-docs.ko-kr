---
title: 'Cdynamicparameteraccessor:: Getparam | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
dev_langs:
- C++
helpviewer_keywords:
- GetParam method
ms.assetid: 893a6bf8-7b55-4f6d-8a10-a43b13be7f56
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a54da47714be4f0230145b3aa5d8b66df44e3679
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicparameteraccessorgetparam"></a>CDynamicParameterAccessor::GetParam
매개 변수 버퍼에서 지정 된 매개 변수에 대 한 문자열이 아닌 데이터를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,   
  ctype* pData) const throw();  

template <class ctype> bool GetParam(TCHAR* pParamName,   
   ctype* pData) const throw();  

void* GetParam(DBORDINAL nParam) const throw();  

void* GetParam(TCHAR* pParamName) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ctype`  
 데이터 형식이 템플릿 매개 변수입니다.  
  
 `nParam`  
 [in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예에 대 한 합니다.  
  
 `pParamName`  
 [in] 매개 변수 이름입니다.  
  
 `pData`  
 [out] 버퍼에서 검색 한 데이터를 포함 하는 메모리 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 템플릿이 아닌 버전에 대 한 데이터를 포함 하는 메모리를 가리킵니다 버퍼에서 검색 됩니다. 템플릿 기반 버전에 대 한 반환 **true** 성공 또는 **false** 실패 합니다.  
  
 사용 하 여 `GetParam` 버퍼에서 문자열이 아닌 매개 변수 데이터를 검색 합니다. 사용 하 여 [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) 버퍼에서 문자열 매개 변수 데이터를 검색 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)