---
title: "Oracle 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "연결[C++], 데이터베이스"
  - "데이터베이스 연결[C++], Oracle"
  - "데이터베이스[C++], 연결"
  - "Oracle[C++], 연결 만들기"
  - "Oracle 데이터베이스[C++]"
  - "Oracle 데이터베이스[C++], 연결"
ms.assetid: d317e763-44aa-47c9-abe8-261d513d894f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Oracle 연결
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Oracle ODBC DSN이나 OLE DB 연결을 구성하려면 Oracle의 SQL\*Net 클라이언트 쪽 구성 요소가 설치되어 있어야 합니다.  SQL\*Net은 Oracle의 네트워크 전송 계층입니다.  Microsoft의 드라이버와 Microsoft OLE DB Oracle 공급자 맵을 비롯하여 대부분의 Oracle ODBC 드라이버는 이 SQL\*Net 계층을 직접 호출합니다.  
  
 SQL\*Net을 구성하면 SQL\*Net 연결 문자열을 기록하십시오.  일반적으로 이 문자열은 Oracle 데이터베이스 서버 이름에 대한 지정자와 네트워크 프로토콜 종류\(TCP\/IP, 명명된 파이프 등\)로 구성됩니다.  대부분 SQL\*Net 연결 문자열은 별칭으로 매핑됩니다.  별칭으로 매핑될 경우에는 별칭만 기록하면 됩니다.  SQL\*Net 구성 방법에 대한 자세한 내용은 Oracle DBA에 문의하거나, SQL\*Net 설명서를 참조하거나, Oracle ODBC 드라이버 도움말 파일에서 연결 문자열 예제를 참조하십시오.  
  
## 참고 항목  
 [데이터베이스 연결 만들기](../../data/ado-rdo/creating-database-connections.md)