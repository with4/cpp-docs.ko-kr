---
title: 'Cdynamicparameteraccessor:: Getparamtype | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicParameterAccessor.GetParamType
- CDynamicParameterAccessor:GetParamType
- CDynamicParameterAccessor::GetParamType
- ATL.CDynamicParameterAccessor.GetParamType
- GetParamType
- ATL::CDynamicParameterAccessor::GetParamType
dev_langs:
- C++
helpviewer_keywords:
- GetParamType method
ms.assetid: d9c46775-c2a6-4100-8b69-99f13c52958b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0c5c531cb053397c2629c3232e41b8976fe947c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicparameteraccessorgetparamtype"></a>CDynamicParameterAccessor::GetParamType
지정된 매개 변수의 데이터 형식을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```
bool GetParamType(DBORDINAL nParam,  
  DBTYPE* pType) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nParam`  
 [in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예에 대 한 합니다.  
  
 `pType`  
 [out] 지정된 된 매개 변수의 데이터 형식을 포함 하는 변수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 **true** 성공 또는 **false** 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)