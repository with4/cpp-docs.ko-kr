---
title: "데이터베이스 응용 프로그램을 만들기 위한 작업 시퀀스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3403807e38f59abc68bf93f510476951c5ec8ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>데이터베이스 응용 프로그램을 만드는 작업 시퀀스
다음 표에서 사용자의 역할와 프레임 워크의 데이터베이스 응용 프로그램을 보여 줍니다.  
  
> [!NOTE]
>  Visual c + + 환경 및 마법사 (DAO 클래스에 포함 되어 있으며 계속 사용할 수 있습니다) 이지만 DAO을 지원 하지 않습니다. 새 MFC 프로젝트에 대 한 ODBC를 사용 하는 것이 좋습니다. DAO는 기존 응용 프로그램 유지 관리만 사용할 수 있습니다.  
  
### <a name="creating-database-applications"></a>데이터베이스 응용 프로그램 만들기  
  
|작업|너 해|프레임 워크|  
|----------|------------|------------------------|  
|MFC ODBC 또는 DAO 클래스를 사용할 것인지 결정 합니다.|ODBC를 사용 하 여 새 MFC 프로젝트에 대 한 합니다. DAO를 사용 하 여 기존 응용 프로그램을 유지 하기 위해서만. 일반 정보에 대 한 문서를 참조 [데이터 액세스 프로그래밍](../data/data-access-programming-mfc-atl.md)합니다.|프레임 워크는 데이터베이스 액세스를 지 원하는 클래스를 제공 합니다.|  
|Database 옵션과 함께 기초 응용 프로그램을 만듭니다.|MFC 응용 프로그램 마법사를 실행 합니다. 데이터베이스 지원 페이지에서 옵션을 선택 합니다. 레코드 뷰를 만드는 옵션을 선택 하는 경우 지정.<br /><br /> -데이터 소스 및 테이블 이름 또는 이름<br />-쿼리 이름입니다.|MFC 응용 프로그램 마법사 파일을 만들고 필요한 포함 하도록 지정 합니다. 지정한 옵션에 따라 파일 레코드 집합 클래스를 포함할 수 있습니다.|  
|데이터베이스 폼 이나 폼을 디자인 합니다.|Visual c + + 대화 상자 편집기를 사용 하 여 레코드 뷰 클래스에 대 한 대화 상자 템플릿 리소스에 컨트롤을 배치 합니다.|MFC 응용 프로그램 마법사를 입력 하는 빈 대화 상자 템플릿 리소스를 만듭니다.|  
|필요에 따라 추가 레코드 뷰 및 레코드 집합 클래스를 만듭니다.|클래스 뷰를 사용 하 여 편집기 뷰를 디자인 하는 클래스 및 대화 상자를 만들 수 있습니다.|클래스 뷰 새 클래스에 대 한 추가 파일을 만듭니다.|  
|코드에서 필요에 따라 레코드 집합 개체를 만듭니다. 각 레코드 집합을 사용 하 여 레코드를 조작할 중...|레코드 집합에서 파생 된 클래스를 기반 [CRecordset](../mfc/reference/crecordset-class.md) 는 마법사를 포함 합니다.|ODBC 레코드 필드 교환 (RFX)를 사용 하 여 레코드 집합의 필드 데이터 멤버는 데이터베이스와 데이터를 교환 합니다. 레코드 뷰를 사용 하는 경우 대화 상자 데이터 교환 (DDX) 레코드 집합 및 레코드 뷰 컨트롤 간에 데이터를 교환 합니다.|  
|... 및 명시적 만들 [CDatabase](../mfc/reference/cdatabase-class.md) 열려는 각 데이터베이스에 대 한 코드에서 합니다.|Recordset 개체는 데이터베이스 개체에 기반 합니다.|데이터베이스 개체는 데이터 원본에 대 한 인터페이스를 제공합니다.|  
|데이터 열을 레코드 집합을 동적으로 바인딩하십시오.|Odbc에서 바인딩을 관리 하는 파생 된 레코드 집합 클래스에 코드를 추가 합니다. 문서 참조 [레코드 집합: 데이터 열 동적 바인딩 (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)합니다.||  
  
## <a name="see-also"></a>참고 항목  
 [프레임 워크에서 빌드](../mfc/building-on-the-framework.md)   
 [MFC 응용 프로그램을 빌드하기 위한 작업 시퀀스](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [OLE 응용 프로그램을 만들기 위한 작업 시퀀스](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [ActiveX 컨트롤을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-activex-controls.md)
