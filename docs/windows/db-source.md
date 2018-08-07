---
title: db_source | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b826e5d630b52062892001c26efda01b5c7293f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873721"
---
# <a name="dbsource"></a>db_source
데이터 원본에 대 한 연결을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ db_source(   
   db_source,   
   name,   
   hresult   
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *db_source*  
 데이터 원본에 연결 하는 데 사용 되는 연결 문자열입니다. 연결 문자열의 형식에 대 한 참조 [연결 문자열 및 데이터 연결](https://msdn.microsoft.com/en-us/library/ms718376.aspx) 에 Microsoft 데이터 액세스 구성 요소 (MDAC) SDK입니다.  
  
 *name* (선택 사항)  
 사용 하는 경우 `db_source` 클래스, *이름* 있는 데이터 원본 개체의 인스턴스가 `db_source` 특성 (예 1 참조)에 적용 합니다. 사용 하는 경우 `db_source` 메서드 구현에서 인라인 *이름* 는 데이터에 액세스 하는 데 사용할 수 있는 변수 (로컬 메서드에) 원본 (예 2 참조). 이 전달할 *이름* 에 `source_name` 의 매개 변수 **db_command** 명령을 사용 하 여 데이터 원본 연결 합니다.  
  
 `hresult` (선택 사항)  
 이 데이터베이스 명령의 `HRESULT`를 수신할 변수를 식별합니다. 변수가 없으면 특성에 의해 자동으로 삽입됩니다.  
  
## <a name="remarks"></a>설명  
 `db_source` 만듭니다는 [CDataSource](../data/oledb/cdatasource-class.md) 및 [CSession](../data/oledb/csession-class.md) 함께 OLE DB 소비자 데이터 원본과 연결을 나타내는 개체입니다.  
  
 사용 하는 경우 `db_source` 는 클래스에는 `CSession` 개체 클래스의 구성원이 됩니다.  
  
 사용 하는 경우 `db_source` 메서드 범위 내에서 실행 되므로 삽입 된 코드 메서드, 및 `CSession` 지역 변수로 개체가 만들어집니다.  
  
 `db_source` 클래스 또는 메서드 내에서 데이터 원본 속성을 추가합니다. 와 함께에서 사용 되는 **db_command** (이 `db_source` *이름* 매개 변수로 해당 `source_name` 매개 변수).  
  
 컴파일러는 클래스를 이름을 소비자 특성 공급자 클래스에이 특성을 적용 하는 경우 \_ *YourClassName*접근자 여기서 *YourClassName* 제공한 이름인는 클래스 및 컴파일러 라는 클래스를 만들 수도 됩니다 *YourClassName*에서 파생 되는 \_ *YourClassName*접근자입니다.  클래스 뷰에 두 클래스 모두 표시됩니다.  
  
 응용 프로그램에서 사용 되는이 특성의 예를 들어 샘플을 참조 하십시오. [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409) 및 [MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e)합니다.  
  
## <a name="example"></a>예제  
 이 샘플에서는 호출 `db_source` 를 데이터 원본에 대 한 연결을 만드는 클래스 `ds` Northwind 데이터베이스를 사용 하 여 합니다. `ds` 내부적으로 사용 될 수 있는 데이터 원본에 대 한 핸들은 `CMyCommand` 클래스입니다.  
  
```  
// db_source_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[  
  db_source(L"my_connection_string", name="ds"),  
  db_command(L"select * from Products")  
]  
class CMyCommand {};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, `struct`, 멤버, 메서드, 로컬|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 특성](../windows/ole-db-consumer-attributes.md)   
