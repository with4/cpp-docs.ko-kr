---
title: 'Cdatasource:: Getinitializationstring | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
dev_langs:
- C++
helpviewer_keywords:
- GetInitializationString method
ms.assetid: 97134723-6e99-4004-a56d-ec57543dbf3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c2cc4652dcb7450217fd99969089bdbeb41c3a3f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094054"
---
# <a name="cdatasourcegetinitializationstring"></a>CDataSource::GetInitializationString
현재 열려 있는 데이터 원본 초기화 문자열을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetInitializationString(BSTR* pInitializationString,   
   bool bIncludePassword = false) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *pInitializationString*  
 [out] 초기화 문자열에 대 한 포인터입니다.  
  
 *bIncludePassword*  
 [in] **true** 문자열에 암호를 포함 하는 경우 그러지 않으면 **false**합니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 초기화 문자열 결과를 나중에이 데이터 원본 연결을 다시 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)