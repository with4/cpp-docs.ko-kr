---
title: "ODBC 및 데이터베이스 클래스 | Microsoft Docs"
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
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e3041a4fc027a8786fb62db7df6eaf486633ce97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-and-the-database-classes"></a>ODBC 및 데이터베이스 클래스
ODBC API 함수 호출이 일반적으로 하는 것 직접 멤버에서의 기능을 캡슐화 하는 MFC ODBC 데이터베이스 클래스는 [CDatabase](../../mfc/reference/cdatabase-class.md) 및 [CRecordset](../../mfc/reference/crecordset-class.md) 클래스입니다. 예를 들어 복잡 한 ODBC 호출 시퀀스, 저장소 위치, 오류 조건 처리 및 기타 작업에 반환 되는 레코드의 바인딩을 관리 사용자에 대 한 데이터베이스 클래스 합니다. 훨씬 단순한 클래스 인터페이스를 사용 하 여 recordset 개체를 통해 레코드를 조작 하는 결과적으로, 합니다.  
  
> [!NOTE]
>  ODBC 데이터 소스는이 항목에 설명 된 대로 MFC ODBC 클래스를 통해 또는 MFC 데이터 액세스 개체 (DAO) 클래스를 통해 액세스할 수 있습니다.  
  
 데이터베이스 클래스 ODBC 기능을 캡슐화 하지만 ODBC API 함수에 대 한 일대일 매핑을 제공 하지 않습니다. 데이터베이스 클래스는 더 높은 수준의 데이터 액세스 개체는 Microsoft Access 및 Microsoft Visual Basic에서 찾지 못한 이후 모델링 추상화를 제공 합니다. 자세한 내용은 참조 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ODBC 기본 사항](../../data/odbc/odbc-basics.md)