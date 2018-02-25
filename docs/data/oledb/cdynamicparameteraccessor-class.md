---
title: "CDynamicParameterAccessor 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 02/14/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicParameterAccessor class
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18f53ca6d95d215ad41c6b2501245be0e470bbb1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor 클래스

비슷한 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) 가져오는 매개 변수 정보를 호출 하 여 설정할 수 있지만 [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-cdynamicparameteraccessor.md)|생성자입니다.|
|[GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md)|버퍼에서 매개 변수 데이터를 검색합니다.|
|[GetParamCount](../../data/oledb/cdynamicparameteraccessor-getparamcount.md)|접근자에서 매개 변수 개수를 검색합니다.|
|[GetParamIO](../../data/oledb/cdynamicparameteraccessor-getparamio.md)|지정된 매개 변수가 입력 매개 변수인지 출력 매개 변수인지를 결정합니다.|
|[GetParamLength](../../data/oledb/cdynamicparameteraccessor-getparamlength.md)|버퍼에 저장된 지정된 매개 변수의 길이를 검색합니다.|
|[GetParamName](../../data/oledb/cdynamicparameteraccessor-getparamname.md)|지정된 매개 변수의 이름을 검색합니다.|
|[GetParamStatus](../../data/oledb/cdynamicparameteraccessor-getparamstatus.md)|버퍼에 저장된 지정된 매개 변수의 상태를 검색합니다.|
|[GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md)|버퍼에 저장된 지정된 매개 변수의 문자열 데이터를 검색합니다.|
|[GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)|지정된 매개 변수의 데이터 형식을 검색합니다.|
|[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)|매개 변수 데이터를 사용하여 버퍼를 설정합니다.|
|[SetParamLength](../../data/oledb/cdynamicparameteraccessor-setparamlength.md)|버퍼에 저장된 지정된 매개 변수의 길이를 설정합니다.|
|[SetParamStatus](../../data/oledb/cdynamicparameteraccessor-setparamstatus.md)|버퍼에 저장된 지정된 매개 변수의 상태를 설정합니다.|
|[SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md)|버퍼에 저장된 지정된 매개 변수의 문자열 데이터를 설정합니다.|

## <a name="remarks"></a>설명

공급자는 이 클래스를 사용할 소비자에 대해 `ICommandWithParameters` 를 지원해야 합니다.

매개 변수 정보는 이 클래스로 만들고 관리하는 버퍼에 저장됩니다. [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) 및 [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)을 사용하여 버퍼에서 매개 변수 데이터를 가져옵니다.

이 클래스는 SQL Server 저장 프로시저를 실행 하 고 출력 매개 변수 값을 가져올를 사용 하는 방법을 보여 주는 예제를 참조 하십시오.는 [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) 샘플의 코드는 [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) GitHub의 리포지토리를 제공 합니다.

## <a name="requirements"></a>요구 사항

**헤더**: atldbcli.h

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)  
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)  
[CAccessor 클래스](../../data/oledb/caccessor-class.md)  
[CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)  
[CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)  
