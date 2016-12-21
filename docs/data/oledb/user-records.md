---
title: "사용자 레코드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "접근자[C++], 행 집합"
  - "접근자[C++], static"
  - "BEGIN_ACCESSOR 매크로, 예제"
  - "BEGIN_ACCESSOR_MAP 매크로"
  - "CAccessor 클래스, 예제"
  - "COLUMN_ENTRY 매크로"
  - "COLUMN_ENTRY_MAP 매크로"
  - "OLE DB 소비자 템플릿, 사용자 레코드"
  - "행 집합[C++], 접근자"
  - "사용자 레코드, OLE DB 소비자 템플릿"
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 사용자 레코드
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정적 액세스, 즉 **CAccessor**에서 파생된 접근자를 사용하려면 소비자는 사용자 레코드을 가지고 있어야만 합니다.  사용자 레코드는 입력이나 출력을 처리하기 위해 데이터 요소를 가지고 있는 C\+\+ 클래스입니다.  ATL OLE DB 소비자 마법사는 소비자를 위해 사용자 레코드를 생성합니다.  명령 처리 같은 선택적 작업을 위해 사용자 레코드에 메서드를 추가할 수 있습니다.  
  
 다음 코드에서는 명령을 처리하는 샘플 레코드를 보여 줍니다.  사용자 레코드에서 `BEGIN_COLUMN_MAP`은 공급자에서 소비자로 전달된 데이터 행 집합을 나타냅니다.  `BEGIN_PARAM_MAP`은 명령 매개 변수의 집합을 나타냅니다.  이 예제에서는 [CCommand](../../data/oledb/ccommand-class.md) 클래스를 사용하여 명령 매개 변수를 처리합니다.  맵 엔트리의 데이터 맴버는 클래스의 각 인스턴스에 대한 메모리의 연속 블록 하나로의 오프셋을 나타냅니다.  `COLUMN_ENTRY` 매크로는 공급자의 `PROVIDER_COLUMN_ENTRY` 매크로에 해당됩니다.  
  
 **COLUMN\_MAP** 및 **PARAM\_MAP** 매크로에 대한 자세한 내용은 [OLE DB 소비자 템플릿의 매크로](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)를 참조하십시오.  
  
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
  
## 마법사 생성 사용자 레코드  
 ATL OLE DB 소비자 마법사를 사용하여 소비자를 생성하려면 OLE DB 템플릿을 사용하거나 OLE DB 특성을 사용할 수 있습니다.  두 경우 생성된 코드가 달라집니다.  이 코드에 대한 자세한 내용은 [소비자 마법사 생성 클래스](../../data/oledb/consumer-wizard-generated-classes.md)를 참조하십시오.  
  
## 여러 접근자에 대한 사용자 레코드 지원  
 여러 접근자를 사용하는 시나리오에 대한 자세한 내용은 [행 집합에서 여러 접근자 사용](../../data/oledb/using-multiple-accessors-on-a-rowset.md)을 참조하십시오.  
  
 다음 예제에서는 행 집합에서 여러 접근자를 지원하도록 수정된 사용자 레코드를 보여 줍니다.  `BEGIN_COLUMN_MAP` 및 `END_COLUMN_MAP` 대신, 각 접근자에 대해 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md) 및 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)를 사용합니다.  `BEGIN_ACCESSOR` 매크로는 접근자 번호\(0으로부터의 오프셋\) 및 접근자가 자동 접근자인지의 여부를 지정합니다.  자동 접근자는 [MoveNext](../../data/oledb/crowset-movenext.md)가 호출되면 `GetData`를 호출하여 자동으로 데이터를 검색합니다.  자동이 아닌 접근자인 경우에는 명시적으로 데이터를 검색해야 합니다.  대형 데이터 필드\(예: 비트맵 이미지\)에 바인딩하는 경우 모든 레코드를 검색하지 않으려면 자동이 아닌 접근자를 사용하십시오.  
  
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
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)