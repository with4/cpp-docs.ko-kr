---
title: 'ODBC: ODBC API를 호출 함수를 직접 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC API functions [C++], calling
- ODBC [C++], catalog functions
- ODBC API functions [C++]
- APIs [C++], calling
- ODBC classes [C++], vs. ODBC API
- direct ODBC API calls
- catalog functions (ODBC)
- catalog functions (ODBC), calling
- ODBC [C++], API functions
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 55b95c5dd48631f9c724aebd163ce948c3469850
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089720"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: ODBC API 함수 직접 호출
데이터베이스 클래스에서 제공 하는 간단한 인터페이스는 [데이터 소스](../../data/odbc/data-source-odbc.md) 는 ODBC 보다 합니다. 결과적으로 클래스는 모든 ODBC API를 캡슐화 하지 않습니다. 클래스의 기능 외부에 있는 모든 기능에 대 한 ODBC API 함수를 직접 호출 해야 합니다. ODBC 카탈로그 함수를 호출 해야 하는 예를 들어 (**:: SQLColumns**, **:: SQLProcedures**, **:: SQLTables**, 및 기타) 직접 합니다.  
  
> [!NOTE]
>  ODBC 데이터 소스는이 항목에 설명 된 대로 MFC ODBC 클래스를 통해 또는 MFC 데이터 액세스 개체 (DAO) 클래스를 통해 액세스할 수 있습니다.  
  
 를 직접 ODBC API 함수를 호출 하려면 프레임 워크 없이 호출 된 경우 수행할 동일한 단계를 수행 해야 합니다. 이러한 단계는:  
  
-   호출에서 반환 된 결과 대 한 저장소를 할당 합니다.  
  
-   ODBC 전달 **HDBC** 또는 **HSTMT** 함수의 매개 변수 시그니처에 따라 처리 합니다. 사용 하 여는 [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) ODBC 핸들을 검색 하는 매크로입니다.  
  
     멤버 변수 **CDatabase::m_hdbc** 및 **CRecordset::m_hstmt** 를 사용 하 여 할당 하 고 이러한 직접 초기화할 필요가 없습니다.  
  
-   아마도 준비 하거나 기본 호출을 수행 하는 추가 ODBC 함수를 호출 합니다.  
  
-   완료 하면 저장소 할당을 취소 합니다.  
  
 이러한 단계에 대 한 자세한 내용은 참조는 [ODBC Open Database Connectivity ()](https://msdn.microsoft.com/en-us/library/ms710252.aspx) MSDN 설명서에서 SDK입니다.  
  
 이러한 단계 외에 하 고 함수의 반환 값, 프로그램을 완료 하는 비동기 호출에 대 한 기다리고 있지 않으면 추가적인 단계가 필요 합니다. 사용 하 여이 마지막 단계를 단순화할 수 있습니다는 `AFX_SQL_ASYNC` 및 `AFX_SQL_SYNC` 매크로입니다. 자세한 내용은 참조 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md) 에 *MFC 참조*합니다.  

  
## <a name="see-also"></a>참고 항목  
 [ODBC 기본 사항](../../data/odbc/odbc-basics.md)
