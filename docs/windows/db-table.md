---
title: db_table | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_table
dev_langs:
- C++
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81379a6da96b084239a083bc930cf8e792d518a2
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649753"
---
# <a name="dbtable"></a>db_table
OLE DB 테이블을 엽니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[ db_table(   
   db_table,   
   name,   
   source_name,   
   hresult   
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *db_table*  
 (예: "제품") 데이터베이스 테이블의 이름을 지정 하는 문자열입니다.  
  
 *name* (선택 사항)  
 테이블 작업에 사용할 핸들의 이름입니다. 둘 이상의 결과 행을 반환 하려는 경우이 매개 변수를 지정 해야 합니다. **db_table** 지정 된 변수를 생성 *이름을* 행 집합을 이동 하거나 여러 작업 쿼리 실행에 사용할 수 있는 합니다.  
  
 *source_name* (선택 사항)  
 `CSession` 특성이 적용되어 명령이 실행되는 클래스의 `db_source` 변수 또는 인스턴스. [db_source](../windows/db-source.md)를 참조하세요.  
  
 *hresult* (선택 사항)  
 이 데이터베이스 명령의 HRESULT 받을 변수를 식별 합니다. 변수가 없으면 특성에 의해 자동으로 삽입됩니다.  
  
## <a name="remarks"></a>설명  
 **db_table** 만듭니다는 [CTable](../data/oledb/ctable-class.md) OLE DB 소비자는 테이블 열에 사용 되는 개체입니다. 이 특성을 사용 하 여 클래스 수준에서만 인라인을 사용할 수 없습니다. 사용 하 여 `db_column` 열을 바인딩할 테이블 변수를 사용 하 여 `db_param` 구분 하려면 (설정 매개 변수 형식 등) 매개 변수입니다.  
  
 컴파일러는 클래스 이름을 소비자 특성 공급자가이 특성 클래스에 적용 될 때 \_ *YourClassName*접근자를 여기서 *YourClassName* 제공한 이름인는 클래스 및 컴파일러 라는 클래스를 만들 수도 됩니다 *YourClassName*에서 파생 되는 \_ *YourClassName*접근자입니다.  클래스 뷰에 두 클래스 모두 표시됩니다.  
  
## <a name="example"></a>예  
 다음 예에서는 Products 테이블에서 사용 하기 위해 엽니다 `CProducts`합니다.  
  
```cpp  
// db_table.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_table(L"dbo.Products") ]  
class CProducts {  
   [ db_column("1") ] LONG m_ProductID;  
};  
```  
  
 응용 프로그램에서 사용 되는이 특성의 예로, 샘플을 참조 하세요 [AtlAgent](http://msdn.microsoft.com/52bef5da-c1a0-4223-b4e6-9e464b6db409) 하 고 [MultiRead](http://msdn.microsoft.com/5a2a915a-77dc-492f-94b2-1b809995dd5e)합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, **구조체**|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 특성](../windows/ole-db-consumer-attributes.md)   