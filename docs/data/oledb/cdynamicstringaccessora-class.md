---
title: CDynamicStringAccessorA 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorA
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e56f71a427fda2444992cc0ed2c3b6166993af1d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341025"
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA 클래스
이 기능을 사용 하면 데이터베이스 스키마 (내부 구조)에 대 한 지식이 없는 경우 데이터 소스에 액세스할 수 있습니다.  
  
## <a name="syntax"></a>구문

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## <a name="remarks"></a>설명  
 공급자 문자열 데이터로 데이터 저장소에서 액세스 하는 모든 데이터를 인출 하는 요청 모두 있지만 `CDynamicStringAccessor` 요청 ANSI 문자열 데이터입니다.  
  
 `CDynamicStringAccessorA` 상속 `GetString` 하 고 `SetString` 에서 `CDynamicStringAccessor`합니다. 이러한 메서드를 사용 하는 경우는 `CDynamicStringAccessorA` 개체를 ***BaseType*** 됩니다 **CHAR**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor 클래스](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor Class](../../data/oledb/cdynamicstringaccessor-class.md)