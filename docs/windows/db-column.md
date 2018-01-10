---
title: db_column | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.db_column
dev_langs: C++
helpviewer_keywords: db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5fe2d3c5edb4b90676c3880ae422c1fb507cd164
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dbcolumn"></a>db_column
행 집합의 변수를 지정된 된 열을 바인딩합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ db_column(   
   ordinal,   
   dbtype,   
   precision,   
   scale,   
   status,   
   length   
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ordinal`  
 서 수 열 번호 (**DBCOLUMNINFO** 서 수) 또는 열 이름 (ANSI 또는 유니코드 문자열)를 바인딩할 데이터를 행 집합의 필드에 해당 합니다. 숫자를 사용 하는 경우 연속 된 서 수를 건너뛸 수 있습니다 (예: 1, 2, 3, 5). 이름을 사용 하는 OLE DB 공급자가 지 원하는 경우 공백을 포함할 수 있습니다. 예를 들어, 다음 형식 중 하나를 사용할 수 있습니다.  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
 *dbtype* (선택 사항)  
 OLE DB [유형 표시기](https://msdn.microsoft.com/en-us/library/ms711251.aspx) 열 항목에 대 한 합니다.  
  
 *전체 자릿수* (선택 사항)  
 열 항목에 사용할 전체 자릿수입니다. 자세한 내용은 설명을 참조는 `bPrecision` 의 요소는 [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *배율* (선택 사항)  
 열 항목에 사용할 소수 자릿수입니다. 자세한 내용은 설명을 참조 `bScale` 의 요소는 [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *상태* (선택 사항)  
 이 열의 상태를 유지 하기 위해 사용 하는 멤버 변수입니다. 상태 인지를 나타냅니다 열 값 데이터 값 이나 다른 값으로 같은 **NULL**합니다. 가능한 값에 대 한 참조 [상태](https://msdn.microsoft.com/en-us/library/ms722617.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 *길이* (선택 사항)  
 열 크기 (바이트)를 저장 하는 데 사용 되는 멤버 변수입니다.  
  
## <a name="remarks"></a>설명  
 **db_column** 행 집합의 변수에 지정 된 테이블 열에 바인딩합니다. OLE DB에 참여할 수 있는 멤버 데이터를 구분 `IAccessor`-바인딩을 기반으로 합니다. 일반적으로 OLE DB 소비자 매크로 사용 하 여 정의 된 열 지도를 설정 하는이 특성 [BEGIN_COLUMN_MAP](../data/oledb/begin-column-map.md), [END_COLUMN_MAP](../data/oledb/end-column-map.md), 및 [COLUMN_ENTRY](../data/oledb/column-entry.md)합니다. OLE DB를 조작 하는 이러한 [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx) 지정된 된 열을 바인딩할 합니다. 로 표시 하는 각 멤버는 **db_column** 특성 열 항목의 형태로 열 지도에 하나의 항목을 차지 합니다. 따라서 호출이 특성 위치에 추가 하면 열 맵을 즉, 명령 또는 테이블 클래스입니다.  
  
 사용 하 여 **db_column** 함께 중 하나는 [db_table](../windows/db-table.md) 또는 [db_command](../windows/db-command.md) 특성입니다.  
  
 컴파일러는 클래스를 이름을 소비자 특성 공급자 클래스에이 특성을 적용 하는 경우 \_ *YourClassName*접근자 여기서 *YourClassName* 제공한 이름인는 클래스 및 컴파일러 라는 클래스를 만들 수도 됩니다 *YourClassName*에서 파생 되는 \_ *YourClassName*접근자입니다.  클래스 뷰에 두 클래스 모두 표시됩니다.  
  
 샘플을 참조 하는 응용 프로그램에서 사용 되는이 특성의 예에 대 한 [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409), 및 [MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e)합니다.  
  
## <a name="example"></a>예  
 이 샘플 테이블의 열을 바인딩하는 **긴** 데이터 멤버 상태 및 길이 필드를 지정 합니다.  
  
```  
// db_column_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   DBSTATUS m_dwProductIDStatus;  
   DBLENGTH m_dwProductIDLength;  
  
   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;  
};  
```  
  
## <a name="example"></a>예  
 이 샘플에는 4 번째 열에 바인딩하는 **긴**, 문자열, 타임 스탬프 및 **DB_NUMERIC** 그 순서 대로 정수입니다.  
  
```  
// db_column_2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   [db_column("1")] LONG m_OrderID;  
   [db_column("2")] TCHAR m_CustomerID[6];  
   [db_column("4")] DB_NUMERIC m_OrderDate;     
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, `struct`, 멤버, 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 특성](../windows/ole-db-consumer-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
