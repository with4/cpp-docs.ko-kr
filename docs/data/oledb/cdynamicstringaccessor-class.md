---
title: "CDynamicStringAccessor 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicStringAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessor class
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 72ca3d1626b22f286a7e1ca9a276582d68cd7619
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicstringaccessor-class"></a>CDynamicStringAccessor 클래스
데이터베이스 스키마(데이터베이스의 내부 구조)에 대해 모를 때 데이터 소스에 액세스할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      template< typename BaseType, DBTYPEENUM OleDbType >  
class CDynamicStringAccessorT : public CDynamicAccessor  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)|지정된 열 데이터를 문자열로 검색합니다.|  
|[SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)|지정된 열 데이터를 문자열로 설정합니다.|  
  
## <a name="remarks"></a>설명  
 반면 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) 공급자가 보고 한 원시 형식으로 데이터를 요청 `CDynamicStringAccessor` 는 공급자 문자열 데이터로 데이터 저장소에서 액세스 하는 모든 데이터를 인출 하는 요청입니다. 값 표시 하거나 데이터 저장소의 내용을 인쇄와 같은 데이터 저장소에 있지 않음 계산이 필요 하지 않은 간단한 작업에 특히 유용 합니다.  
  
 데이터 저장소에 있는 열 데이터의 네이티브 형식은 중요하지 않습니다. 공급자가 데이터 변환을 지원할 수 있는 한 데이터를 문자열 형식으로 제공합니다. 요청 호출이 성공 값을 반환 합니다 공급자를 문자열 (은)를 네이티브 데이터 형식에서의 변환을 지원 하지 않으면, **DB_S_ERRORSOCCURED**, 해당 열에 대 한 상태는 변환 문제가 있음을 나타낼 **DBSTATUS_E_CANTCONVERTVALUE**합니다.  
  
 사용 하 여 `CDynamicStringAccessor` 열 정보를 가져오는 방법입니다. 이 열 정보를 사용 하 여 접근자를 런타임에 동적으로 만듭니다.  
  
 열 정보는이 클래스에서 만들고 관리 하는 버퍼에 저장 됩니다. 사용 하 여 버퍼에서 데이터를 가져올 [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)를 사용 하 여 버퍼에 저장 하거나 [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)합니다.  
  
 에 대 한 설명 및 동적 접근자 클래스 사용 예제를 참조 하세요. [동적 접근자 사용](../../data/oledb/using-dynamic-accessors.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor 클래스](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessorA 클래스](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW 클래스](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CXMLAccessor 클래스](../../data/oledb/cxmlaccessor-class.md)