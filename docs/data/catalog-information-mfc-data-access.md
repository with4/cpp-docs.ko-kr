---
title: "카탈로그 정보  (MFC Data Access) | Microsoft Docs"
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
  - "카탈로그 정보 데이터베이스[C++]"
  - "DAO[C++], 카탈로그 정보"
  - "데이터베이스[C++], 카탈로그 정보 데이터베이스"
  - "ODBC[C++], 카탈로그 정보"
  - "테이블[C++]"
  - "테이블[C++], 카탈로그 정보"
ms.assetid: c184e80f-ff17-409f-9df8-05275080bb8d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 카탈로그 정보  (MFC Data Access)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

데이터 소스의 테이블에 대한 정보에는 테이블 및 테이블 내 열의 이름, 테이블 권한, 기본 키와 외래 키의 이름, 미리 정의된 쿼리나 저장 프로시저에 대한 정보, 테이블의 인덱스 관련 정보, 그리고 테이블 관련 통계가 포함될 수 있습니다.  
  
 자세한 내용은 [데이터 소스: 데이터 소스의 스키마 확인\(ODBC\)](../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)을 참조하세요.  
  
> [!NOTE]
>  MFC DAO 클래스에서 카탈로그 정보를 가져오려는 경우 [CDaoDatabase::GetTableDefCount](../Topic/CDaoDatabase::GetTableDefCount.md) 및 [CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md)를 사용하여 데이터베이스의 테이블을 열거하고 [CDaoTableDefInfo](../mfc/reference/cdaotabledefinfo-structure.md) 구조체에서 각 테이블에 대한 정보를 가져오면 됩니다.  
  
## 참고 항목  
 [데이터 엑세스 프로그래밍 \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)