---
title: 사용자 레코드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_MAP
dev_langs:
- C++
helpviewer_keywords:
- rowsets [C++], accessors
- COLUMN_ENTRY macro
- COLUMN_ENTRY_MAP macro
- user records, OLE DB consumer templates
- OLE DB consumer templates, user records
- CAccessor class, example
- BEGIN_ACCESSOR_MAP macro
- accessors [C++], rowsets
- accessors [C++], static
- BEGIN_ACCESSOR macro, example
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aea6b4b2ebb1a02e4ef669b437fbe7eb30937f9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="user-records"></a>사용자 레코드
정적 접근자를 사용 하려면 (즉,에서 파생 된 접근자 **CAccessor)**, 소비자 사용자 레코드가 있어야 합니다. 사용자 레코드는 핸들 입력 또는 출력에 데이터 요소를 포함 하는 c + + 클래스입니다. ATL OLE DB 소비자 마법사는 소비자에 대 한 사용자 레코드를 생성합니다. 명령 처리 등의 선택적 작업에 대 한 사용자 레코드에 메서드를 추가할 수 있습니다.  
  
 다음 코드는 명령을 처리 하는 샘플 레코드를 보여 줍니다. 사용자 레코드에서 `BEGIN_COLUMN_MAP` 는 공급자에서 소비자에 게 전달 하는 데이터 행 집합을 나타냅니다. `BEGIN_PARAM_MAP` 명령 매개 변수 집합을 나타냅니다. 사용 하 여이 예제는 [CCommand](../../data/oledb/ccommand-class.md) 명령 매개 변수를 처리 하는 클래스입니다. 맵 항목의 데이터 멤버에 하나의 연속 된 메모리 블록을 클래스의 각 인스턴스에 대 한 오프셋을 나타냅니다. `COLUMN_ENTRY` 매크로에 해당 하는 `PROVIDER_COLUMN_ENTRY` 공급자 측의 매크로입니다.  
  
 에 대 한 자세한 내용은 **COLUMN_MAP** 및 **param_map이** 매크로, 참조 [OLE DB 소비자 템플릿에 대 한 매크로](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)합니다.  
  
```  
class CArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_COLUMN_MAP(CArtists)  
   COLUMN_ENTRY(1, m_szFirstName)  
   COLUMN_ENTRY(2, m_szLastName)  
   COLUMN_ENTRY(3, m_nAge)  
END_COLUMN_MAP()  
  
// Parameter binding map  
BEGIN_PARAM_MAP(CArtists)  
   COLUMN_ENTRY(1, m_nAge)  
END_PARAM_MAP()  
};  
```  
  
## <a name="wizard-generated-user-records"></a>마법사에서 생성 된 사용자 레코드  
 ATL OLE DB 소비자 마법사를 사용 하 여 소비자를 생성 하는 경우 OLE DB 템플릿 또는 OLE DB 특성을 사용 하 여 선택할을 수 있습니다. 생성 된 코드는 경우에 따라 다릅니다. 이 코드에 대 한 자세한 내용은 참조 [소비자 마법사 생성 클래스](../../data/oledb/consumer-wizard-generated-classes.md)합니다.  
  
## <a name="user-record-support-for-multiple-accessors"></a>여러 접근자에 대 한 사용자 레코드 지원  
 여러 접근자를 사용 해야 하는 시나리오의 자세한 논의 알려면 [행 집합에서 여러 접근자 사용](../../data/oledb/using-multiple-accessors-on-a-rowset.md)합니다.  
  
 다음 예제에서는 행 집합에서 여러 접근자를 지원 하도록 수정 사용자 레코드를 보여 줍니다. 대신 `BEGIN_COLUMN_MAP` 및 `END_COLUMN_MAP`를 사용 하 여 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md) 및 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 각 접근자에 대 한 합니다. `BEGIN_ACCESSOR` 매크로 접근자 번호 (0부터 오프셋) 및 접근자가 자동 있는지 여부를 지정 합니다. 자동 호출 `GetData` 에 대 한 호출에 자동으로 데이터를 검색 하려면 [MoveNext](../../data/oledb/crowset-movenext.md)합니다. 자동이 아닌 접근자를 사용 하면 명시적으로 데이터를 검색 해야 합니다. 모든 레코드를 검색 하지 않을 (예: 비트맵 이미지) 대형 데이터 필드를 바인딩하는 경우: 접근자를 사용 합니다.  
  
```  
class CMultiArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_ACCESSOR_MAP(CMultiArtists, 2)  
   BEGIN_ACCESSOR(0, true)    // true specifies an auto accessor  
    COLUMN_ENTRY(1, m_szFirstName)  
    COLUMN_ENTRY(2, m_szLastName)  
   END_ACCESSOR()  
   BEGIN_ACCESSOR(1, false)   // false specifies a manual accessor  
    COLUMN_ENTRY(3, m_nAge)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)