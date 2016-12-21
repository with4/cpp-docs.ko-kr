---
title: "단순 행 집합 검색 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "접근자[C++], 행 집합"
  - "데이터 액세스[C++], 행 집합"
  - "OLE DB 소비자[C++], 데이터베이스 특성"
  - "행 집합[C++], 액세스"
  - "단순 행 집합"
ms.assetid: b45acf16-4029-429d-ab8d-b7fba98b9740
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 단순 행 집합 검색
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 예제에서는 명령을 사용하지 않고 데이터베이스에 빠르고 쉽게 액세스하는 방법을 보여 줍니다.  다음 ATL 프로젝트의 소비자 코드는 ODBC 드라이버용 Microsoft OLE DB 공급자를 사용하여 Microsoft Access 데이터베이스의 *Artists*라는 테이블에서 레코드를 검사합니다.  이 코드는 사용자 레코드 클래스 `CArtists`를 기반으로 접근자를 가진 [CTable](../../data/oledb/ctable-class.md) 테이블 개체를 만듭니다.  이 코드는 연결을 열고, 연결된 세션을 열며 세션 상의 테이블을 엽니다.  
  
```  
#include <atldbcli.h>  
  
CDataSource connection;  
CSession session;  
CTable<CAccessor<CArtists> > artists;  
  
// Open the connection, session, and table, specifying authentication   
// using Windows NT integrated security. Hard-coding a password is a major  
// security weakness.  
connection.Open(CLSID_MSDASQL, "NWind", NULL, NULL,   
DBPROP_AUTH_INTEGRATED);  
session.Open(connection);  
artists.Open(session, "Artists");  
  
// Get data from the rowset  
while (artists.MoveNext() == S_OK)  
{  
   cout << artists.m_szFirstName;  
   cout << artists.m_szLastName;  
}  
```  
  
 사용자 레코드 `CArtists`는 다음과 같습니다.  
  
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
```  
  
## 참고 항목  
 [OLE DB 소비자 템플릿 작업](../../data/oledb/working-with-ole-db-consumer-templates.md)