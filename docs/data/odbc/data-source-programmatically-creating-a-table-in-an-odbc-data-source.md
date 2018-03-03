---
title: "프로그래밍 방식으로 ODBC 데이터 원본에 테이블을 만들 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 43be9c8a2339bb47d598304145a8c34f391b11c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>데이터 소스: ODBC 데이터 소스에서 프로그래밍 방식으로 테이블 작성
이 항목에서는 데이터에 대 한 테이블을 만드는 방법을 설명 소스를 사용 하 여는 `ExecuteSQL` 클래스의 멤버 함수 `CDatabase`, 함수가 포함 된 문자열을 전달는 **CREATE TABLE** SQL 문입니다.  
  
 MFC의 ODBC 데이터 원본에 대 한 일반 정보를 참조 하십시오. [데이터 원본 (ODBC)](../../data/odbc/data-source-odbc.md)합니다. 항목 [데이터 소스: 프로그래밍 방식으로 ODBC 데이터 소스 구성](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) 만드는 데이터 원본에 설명 합니다.  
  
 사용 하 여 테이블을 쉽게 만들 수 있는 경우 설정 된 데이터 원본는 `ExecuteSQL` 멤버 함수 및 **CREATE TABLE** SQL 문입니다. 예를 들어, 사용 했던는 `CDatabase` 호출 개체 `myDB`, 다음 MFC 코드를 사용 하 여 테이블을 만들 수 없습니다:  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
 이 코드 예제에서는 Microsoft Access 데이터 원본 연결에서 유지 관리에 "내" 라는 테이블을 `myDB`; 테이블에 두 개의 필드가 "OfficeID" 및 "OfficeName" 포함  
  
> [!NOTE]
>  에 지정 된 필드 형식에서 **CREATE TABLE** SQL 문을 사용 하는 ODBC 드라이버에 따라 다를 수 있습니다. Microsoft Query 프로그램 (Visual c + + 1.5와 함께 배포)는 데이터 원본에 대해 사용할 수 있는 필드 형식과 검색 한 방법입니다. Microsoft 쿼리 클릭 **파일**, 클릭 **테이블**, 데이터 원본에서 테이블을 선택 및에 표시 된 형식을 확인는 **형식** 콤보 상자. SQL 구문이 인덱스를 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 소스(ODBC)](../../data/odbc/data-source-odbc.md)