---
title: 'Cdatasource:: Openfrominitializationstring | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
dev_langs:
- C++
helpviewer_keywords:
- OpenFromInitializationString method
ms.assetid: 5ef1f1fd-92a9-4e1c-ad80-d3601b094b8c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dac964f7c6c863f85769a164fab8c418e1c45430
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090936"
---
# <a name="cdatasourceopenfrominitializationstring"></a>CDataSource::OpenFromInitializationString
사용자가 제공한 초기화 문자열에 지정 된 데이터 원본이 열립니다.  
  
## <a name="syntax"></a>구문  
  
```
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,   
   bool fPromptForInfo= false) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *szInitializationString*  
 [in] 초기화 문자열입니다.  
  
 *fPromptForInfo*  
 [in] 이 인수는로 설정 되어 있으면 **true**, 다음 `OpenFromInitializationString` 는 설정의 **DBPROP_INIT_PROMPT** 속성을 **DBPROMPT_COMPLETEREQUIRED**, 사용자 지정 하는 추가 정보가 필요 하는 경우에 메시지가 표시 됩니다. 이 초기화 문자열에서 암호를 요구 하는 데이터베이스를 지정 하는 경우에 유용 하지만 문자열 암호를 포함 하지 않습니다. 사용자 암호 (또는 다른 누락 된 정보)에 대 한 메시지가 표시 되는 데이터베이스에 연결 하려고 할 때입니다.  
  
 기본값은 **false**를 지정 하는 사용자 라는 메시지가 표시 되지 (설정 **DBPROP_INIT_PROMPT** 를 **DBPROMPT_NOPROMPT**).  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 oledb32.dll에 있는 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다. 이 DLL에는 리소스 풀링, 자동 트랜잭션 참여 등과 같은 서비스 구성 요소 기능의 구현이 들어 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)