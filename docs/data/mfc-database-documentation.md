---
title: "MFC 데이터베이스 설명서 | Microsoft Docs"
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
  - "DAO[C++], MFC"
  - "데이터베이스[C++], MFC"
  - "MFC[C++], 데이터베이스 응용 프로그램"
  - "ODBC[C++], MFC"
ms.assetid: bb120282-cd0d-4bf4-a27c-93b3501fb3a0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC 데이터베이스 설명서
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DAO와 ODBC 클래스에 대한MFC 설명서는 아래 표에 나열된 구성 요소로 이루어집니다.  
  
### MFC 데이터베이스 설명서  
  
|설명서 내용|참조|  
|------------|--------|  
|DAO 및 ODBC의 클래스|MFC Reference에 나와 있는 클래스 이름|  
|DAO 및 ODBC의 전역 함수 및 매크로|MFC Reference에 나와 있는 함수 또는 매크로 이름|  
|MFC ODBC 클래스를 사용한 프로그래밍|[ODBC 및 MFC](../data/odbc/odbc-and-mfc.md)|  
|DAO 및 ODBC에 대한 기술 참고 사항|[MFC 기술 참고 사항](../mfc/technical-notes-by-category.md)|  
  
##  <a name="_core_mfc_documentation_and_dao_documentation"></a> MFC 설명서 및 DAO 설명서  
 MFC DAO 클래스에 대한 MFC 설명서에는 온라인 설명서에 포함된 DAO SDK 설명서의 항목에 대한 참조 사항이 들어 있습니다.  MFC에는 DAO가 캡슐화, 즉 래핑되므로 MFC 설명서의 내용은 다음과 같습니다.  
  
-   MFC에 초점을 맞춰 MFC가 내부 DAO의 구현과 다른 점을 설명합니다.  
  
-   기본적인 세부 정보에 대한 DAO SDK 도움말 항목을 알려 줍니다.  이러한 상호 참조는 항상 "DAO 도움말에서 X 항목을 참조하십시오."라고 표시됩니다.  
  
-   MFC와 DAO의 기능상의 차이점에 대해 설명합니다.  MFC에 DAO의 모든 기능이 래핑되어 있지는 않습니다.  예를 들어, MFC에서는 DAO의 보안 기능에 대한 개체를 제공하지 않습니다.  
  
> [!NOTE]
>  DAO SDK 도움말은 별도의 도움말 파일입니다.  현재 버전의 Visual C\+\+에는 이 설명서에서 DAO 도움말에 연결된 하이퍼텍스트 링크가 없습니다.  
  
> [!NOTE]
>  DAO SDK 도움말 항목을 찾아보는 경우에는 Basic 프로그래밍 언어에 대한 지식이 약간 필요합니다.  이는 DAO SDK 설명서의 예제가 기본적으로 C\+\+가 아닌 Basic 프로그래밍 언어로 작성되어 있기 때문입니다. 그러나, DAO SDK에는 MFC를 사용하지 않는 C\+\+ 예제들도 제공됩니다.  
  
##  <a name="_core_mfc_documentation_and_odbc_documentation"></a> MFC 설명서 및 ODBC 설명서  
 MFC ODBC 클래스에 대한 MFC 설명서의 구성은 다릅니다.  MFC ODBC 클래스는 ODBC API의 래퍼가 아닌 ODBC에 기반한 고급 추상화를 제공합니다.  따라서, 이 두 가지 설명서는 MFC와 DAO 설명서에 비해 연관성이 높지 않습니다.  ODBC 설명서에서는 Basic보다는 C\+\+에 훨씬 가까운 C 언어를 사용합니다.  
  
## 참고 항목  
 [MFC 데이터베이스 클래스\(ODBC 및 DAO\)](../data/mfc-database-classes-odbc-and-dao.md)   
 [ODBC 기초](../data/odbc/odbc-basics.md)