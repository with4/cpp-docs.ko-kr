---
title: 레코드 선택 및 조작 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, selecting
- record selection, MFC ODBC classes
- ODBC recordsets, selecting records
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2a4b76d0b4273e5afb32206336b4aabbfe9294eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090080"
---
# <a name="selecting-and-manipulating-records"></a>레코드 선택 및 조작
일반적으로 선택 하면 레코드 SQL을 사용 하 여 데이터 원본에서 **선택** 결과 집합은 테이블 또는 쿼리에서 레코드 집합을 가져오는 문입니다. 데이터베이스 클래스와 recordset 개체를 사용 하 여 선택 하 고 결과 집합에 액세스 합니다. 이 클래스에서 파생 되는 응용 프로그램 관련 클래스의 개체는 [CRecordset](../../mfc/reference/crecordset-class.md)합니다. 레코드 집합 클래스를 정의할 때와 연결할 데이터 원본를 사용 하려면 테이블 및 테이블의 열을 지정 합니다. MFC 응용 프로그램 마법사 또는 **클래스 추가** (에 설명 된 대로 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) 특정 데이터 원본에 연결 된 클래스를 만듭니다. 마법사에서 작성 된 [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) 클래스의 멤버 함수 `CRecordset` 이름을 반환 하는 테이블입니다. 레코드 집합 클래스를 만드는 마법사를 사용 하는 방법에 대 한 자세한 내용은 참조 [MFC 응용 프로그램 마법사, 데이터베이스 지원](../../mfc/reference/database-support-mfc-application-wizard.md) 및 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)합니다.  
  
 사용 하는 [CRecordset](../../mfc/reference/crecordset-class.md) 개체 런타임 시 수행할 수 있습니다.  
  
-   현재 레코드의 데이터 필드를 검사 합니다.  
  
-   필터링 하거나 레코드 집합을 정렬 합니다.  
  
-   기본 SQL 사용자 지정 **선택** 문.  
  
-   선택 된 레코드를 스크롤하십시오.  
  
-   추가, 업데이트 또는 삭제 레코드 (데이터 원본 및 레코드 집합을 모두 업데이트할 수 있는 경우).  
  
-   레코드 집합 다시 쿼리를 허용 하는지 여부를 테스트 레코드 집합의 내용을 새로 고 치세요.  
  
 레코드 집합 개체를 사용 하 여를 마치면 닫고 소멸 시킵니다. 레코드 집합에 대 한 자세한 내용은 참조 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)