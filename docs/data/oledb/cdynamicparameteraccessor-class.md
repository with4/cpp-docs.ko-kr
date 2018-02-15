---
title: "CDynamicParameterAccessor 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
ms.openlocfilehash: 6c0bf234bd0f8a3de96c545e2bbdfe492822d627
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor 클래스
[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) 와 유사하지만 [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx) 인터페이스를 호출하여 설정한 매개 변수 정보를 가져옵니다.  
  
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
  
 이 클래스를 사용하여 SQL Server 저장 프로시저를 실행하고 출력 매개 변수 값을 가져오는 방법을 보여 주는 예제는 기술 자료 문서 Q058860 "방법: CDynamicParameterAccessor를 사용하여 저장 프로시저 실행"을 참조하세요. 기술 자료 문서는 MSDN Library Visual Studio 설명서나 [http://support.microsoft.com/](http://support.microsoft.com)에서 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor 클래스](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)