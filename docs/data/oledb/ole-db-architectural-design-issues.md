---
title: "OLE DB 아키텍처 설계 문제 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, application design considerations
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2cfb6b8ff4941aff1271662c27dddd509b023c55
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ole-db-architectural-design-issues"></a>OLE DB 아키텍처 설계 문제
OLE DB 응용 프로그램을 시작 하기 전에 다음과 같은 문제를 고려해 야 합니다.  
  
 **OLE DB 응용 프로그램을 작성 하는 데 어떤 프로그래밍 구현을 사용?**  
 Microsoft는이를 위해 여러 개의 라이브러리: OLE DB 템플릿 라이브러리, OLE DB 특성 및 OLE DB SDK에는 원시 OLE DB 인터페이스입니다. 또한 마법사가 프로그램을 작성 하는 데 도움이 되도록 합니다. 이러한 구현은에 설명 된 [OLE DB 템플릿, 특성 및 기타 구현](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md)합니다.  
  
 **사용자 고유의 공급자를 작성 해야 합니까?**  
 대부분의 개발자는 자신의 공급자를 작성할 필요가 없습니다. Microsoft는 여러 공급자를 제공합니다. (예: 소비자 ATL OLE DB 소비자 마법사를 사용 하 여 프로젝트를 추가할 때), 데이터 연결을 만들 때마다는 **데이터 연결 속성** 대화 상자는 시스템에 등록 된 모든 사용 가능한 공급자를 나열 합니다. 사용자의 데이터 저장소 및 데이터 액세스 응용 프로그램에 대 한 적절 한 경우 이러한 공급자 중 하나는 가장 쉬운 방법은 중 하나를 사용 합니다. 그러나 데이터 저장소에 이러한 범주 중 하나를 벗어나는 경우 공급자를 만들 해야 합니다. 공급자를 만드는 방법은 참조 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)합니다.  
  
 **소비자에 대 한 지원의 수준이 필요 한가요?**  
 소비자가 매우 기본적인; 수 있습니다. 반면 다른 매우 복잡할 수 있습니다. OLE DB 개체의 기능 속성으로 지정 됩니다. ATL OLE DB 소비자 마법사를 사용 하 여 공급자를 만들려면 소비자 또는 공급자 마법사를 만들 때 기능의 표준 집합을 부여할 수에 대 한 적절 한 개체 속성을 설정 합니다. 그러나 마법사 생성 소비자 또는 공급자 클래스 작업 수 필요한 모든 지원 하지 않는 경우 해야 해당 클래스에 대 한 인터페이스를 참조 하는 [OLE DB 템플릿 라이브러리](../../data/oledb/ole-db-templates.md)합니다. 이러한 인터페이스를 사용 하 여 보다 쉽게 있습니다에 대 한 추가 구현을 제공 하는 원시 OLE DB 인터페이스를 래핑합니다.  
  
 예를 들어 행 집합의 데이터를 업데이트 하지만 마법사를 사용 하 여 소비자를 만든 경우이 값을 지정 하지 않았습니다 수 기능 사후 설정 하 여 지정 된 **DBPROP_IRowsetChange** 및  **DBPROP_UPDATABILITY** 명령 개체의 속성입니다. 그런 다음 행 집합을 만든 경우에 `IRowsetChange` 인터페이스입니다.  
  
 **다른 데이터 액세스 기술 (예: ADO, ODBC 또는 DAO)를 사용 하 여 이전 코드 있습니까?**  
 기술 (예: ADO 구성 요소를 사용 하 여 OLE DB 구성 요소와 및 OLE DB로 ODBC 코드 마이그레이션)의 가능한 조합을 지정 된 경우 Visual c + + 설명서의 범위를 벗어납니다 모든 상황을 포함 합니다. 그러나 많은 기사 다양 한 시나리오는 다음 Microsoft 웹 사이트에서 사용할 수 있습니다.  
  
-   [Microsoft 도움말 및 지원](http://go.microsoft.com/fwlink/p/?linkid=148218)  
  
-   [Microsoft 데이터 액세스 기술 문서 개요](http://go.microsoft.com/fwlink/p/?linkid=148217)  
  
-   [Visual Studio Solution Center](http://go.microsoft.com/fwlink/p/?linkid=148215)  
  
-   [Microsoft.com 검색](http://search.microsoft.com/)  
  
 검색을 수행 하면 시나리오;에 가장 잘 맞는 키워드의 조합의 입력 하십시오. 예: ADO 개체는 OLE DB 공급자와 함께 사용할 때 부울 검색을 시도와 **ADO 및 "OLE DB"**합니다. 이전 DAO 코드 ODBC 마이그레이션하려는 경우 "모든 단어"를 선택 하 고 문자열을와 같은 지정 **마이그레이션 DAO**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)   
 [OLE DB 프로그래밍 개요](../../data/oledb/ole-db-programming-overview.md)