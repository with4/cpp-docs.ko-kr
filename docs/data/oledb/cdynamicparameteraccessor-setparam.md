---
title: 'Cdynamicparameteraccessor:: Setparam | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
dev_langs:
- C++
helpviewer_keywords:
- SetParam method
ms.assetid: e2349220-545c-46ad-90da-9113ac52551a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3fcedc0d54e5b25eb4490425253f6c1bfd139a85
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicparameteraccessorsetparam"></a>CDynamicParameterAccessor::SetParam
지정된 된 (string이 아닌) 데이터를 사용 하 여 매개 변수 버퍼를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,  
               constctype* pData,  
               DBSTATUS status = DBSTATUS_S_OK) throw();  

template <class ctype>  
bool SetParam(TCHAR* pParamName,  
               const ctype* pData,  
               DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ctype`  
 데이터 형식이 템플릿 매개 변수입니다.  
  
 `nParam`  
 [in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 예:  
  
 [!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]  
  
 `pParamName`  
 [in] 매개 변수 이름입니다.  
  
 `pData`  
 [in] 버퍼에 쓸 데이터를 포함 하는 메모리 포인터입니다.  
  
 *status*  
 [in] `DBSTATUS` 열 상태입니다. 에 대 한 내용은 `DBSTATUS` 값, 참조 [상태](https://msdn.microsoft.com/en-us/library/ms722617.aspx) 에 *OLE DB Programmer's Reference*, 검색 또는 `DBSTATUS` oledb.h에서 합니다.  
  
## <a name="return-value"></a>반환 값  
 반환 **true** 성공 또는 **false** 실패 합니다.  
  
 사용 하 여 `SetParam` 버퍼에 문자열이 아닌 매개 변수 데이터를 설정할 수 있습니다. 사용 하 여 [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) 버퍼에 문자열 매개 변수 데이터를 설정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)