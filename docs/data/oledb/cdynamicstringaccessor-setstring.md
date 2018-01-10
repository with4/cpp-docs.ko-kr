---
title: 'Cdynamicstringaccessor:: Setstring | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
dev_langs: C++
helpviewer_keywords: SetString method
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c05186d8ea7f62ad07cae9a4b4689083543e485
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicstringaccessorsetstring"></a>CDynamicStringAccessor::SetString
지정된 열 데이터를 문자열로 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetString(  
   DBORDINAL nColumn,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const CHAR* pColumnName,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const WCHAR* pColumnName,  
   BaseType* data  
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nColumn`  
 [in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 특수 값 0 있는 경우 책갈피 열을 참조 합니다.  
  
 `pColumnName`  
 [in] 열 이름이 포함 된 문자열에 대 한 포인터입니다.  
  
 `data`  
 [in] 지정된 된 열에 쓸 문자열 데이터에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 지정된 된 열을 설정 하는 문자열 값에 대 한 포인터입니다. 형식의 값은 `BaseType`, 될 `CHAR` 또는 `WCHAR` 인지 여부에 따라 `_UNICODE` 정의 여부.  
  
## <a name="remarks"></a>설명  
 세 번째 재정의 폼은 열 이름을 유니코드 문자열로 및 두 번째 폼은 ANSI 문자열 변수로 열 이름이 재정의 합니다.  
  
 경우 `_SECURE_ATL` 정의 된 0이 아닌 값을 런타임 어설션 오류가 발생 합니다 입력 `data` 문자열이 참조 된 데이터 열의 허용 되는 최대 길이 보다 깁니다. 그렇지 않은 경우 입력된 문자열에 최대 허용 길이 보다 긴 경우 잘립니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicStringAccessor Class](../../data/oledb/cdynamicstringaccessor-class.md)