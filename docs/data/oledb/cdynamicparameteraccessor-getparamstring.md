---
title: 'Cdynamicparameteraccessor:: Getparamstring | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
dev_langs:
- C++
helpviewer_keywords:
- GetParamString method
ms.assetid: 078c2b1c-7072-47c1-a203-f47e75363f91
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 203732a5f8d7b1eea9d8047ccf7dc4cb67f83213
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicparameteraccessorgetparamstring"></a>CDynamicParameterAccessor::GetParamString
버퍼에 저장된 지정된 매개 변수의 문자열 데이터를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```
bool GetParamString(DBORDINAL nParam,  
  CSimpleStringA& strOutput) throw();bool GetParamString(DBORDINAL nParam,  
  CSimpleStringW& strOutput) throw();bool GetParamString(DBORDINAL nParam,  
  CHAR* pBuffer,  
   size_t* pMaxLen) throw();bool GetParamString(DBORDINAL nParam,  
  WCHAR* pBuffer,  
   size_t* pMaxLen) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nParam`  
 [in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예에 대 한 합니다.  
  
 `strOutput`  
 [out] ANSI (**CSimpleStringA**) 또는 유니코드 (**CSimpleStringW**) 문자열 데이터의 지정된 된 매개 변수입니다. 형식의 매개 변수를 전달 해야 `CString`, 예:  
  
 [!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
 `pBuffer`  
 [out] ANSI에 대 한 포인터 (**CHAR**) 또는 유니코드 (**WCHAR**) 문자열 데이터의 지정된 된 매개 변수입니다.  
  
 `pMaxLen`  
 [out] 버퍼의 크기에 대 한 포인터에서 가리키는 `pBuffer` (문자에서 종결 NULL 포함).  
  
## <a name="remarks"></a>설명  
 반환 **true** 성공 또는 **false** 실패 합니다.  
  
 경우 `pBuffer` 가 null 인 경우이 방법은가 가리키는 메모리에 필요한 버퍼 크기를 설정 합니다 `pMaxLen` 다음 다시 돌아와 **true** 데이터를 복사 하지 않고 있습니다.  
  
 경우이 메서드는 사용할 버퍼 `pBuffer` 전체 문자열을 포함할 만큼 크지 않습니다.  
  
 사용 하 여 `GetParamString` 버퍼에서 문자열 매개 변수 데이터를 검색 합니다. 사용 하 여 [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) 버퍼에서 문자열이 아닌 매개 변수 데이터를 검색 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)