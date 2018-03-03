---
title: "MFC ODBC 소비자 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.class.mfc.consumer.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC ODBC Consumer Wizard
- wizards [MFC]
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad9e4aeb15d2af04987883b6554d569e3cc16b8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-odbc-consumer-wizard"></a>MFC ODBC 소비자 마법사
여기에 요약 "검색 결과"를 삽입 합니다.  
  
 이 마법사는 지정 된 데이터 원본에 액세스 하는 데 필요한 ODBC 레코드 집합 클래스 및 데이터 바인딩을 설정 합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **데이터 원본**  
 **데이터 소스** 단추 지정된 된 ODBC 드라이버를 사용 하 여 지정 된 데이터 소스를 설정할 수 있습니다. 데이터 원본 파일 (DSN)에 대 한 자세한 내용은 참조 하십시오. [파일 데이터 원본을](https://msdn.microsoft.com/library/ms715401.aspx) ODBC sdk에서입니다. **데이터 원본 선택** 대화 상자는 두 개의 탭:  
  
-   **파일 데이터 원본** 탭:는 **찾는 위치** 상자에 파일을 사용 하 여 데이터 원본으로 선택할 수 있는 디렉터리를 지정 합니다. 기본값은 \program Files\ODBC\Data 원본. 기존 파일 데이터 소스 (.dsn 파일) 기본 목록 상자에 나타납니다. 데이터 원본을 사용 하 여 미리 설정 하거나는 **파일 DSN** 탭에 [ODBC 데이터 원본 관리자](https://msdn.microsoft.com/library/ms714024.aspx), 또는이 대화 상자를 사용 하 여 새 보고서 만들기.  
  
     이 대화 상자에서 새 파일 데이터 소스를 만들려면 `New` DSN name;을 지정 하는 **새 데이터 원본 만들기** 대화 상자가 나타납니다. 에 **새 데이터 원본 만들기** 대화 상자 적절 한 드라이버를 선택 하 고 클릭 `Next`; 클릭 **찾아보기**, (선택 해야 할 모든 파일을 데이터 원본으로 사용 될 파일의 이름을 선택 하 고 보기 DSN이 아닌 파일과 같은 파일을.xls); 클릭 `Next`, 클릭 하 고 **마침**합니다. (DSN이 아닌 파일을 선택 하는 경우 발생 합니다 "ODBC Microsoft Excel 설정과 같은" DSN에 파일을 변환 하는 드라이버 관련 대화 상자를.)  
  
    > [!NOTE]
    >  또한 ODBC 데이터 원본 관리자를 사용 하 여 미리 파일 데이터 소스를 새로 만들 수 있습니다. **시작** 메뉴 선택 **설정**, **제어판**, **관리 도구**, **데이터 원본 (ODBC)**, 차례로 **ODBC 데이터 원본 관리자**합니다.  
  
     **DSN 이름** 상자를 사용 하는 파일 데이터 원본에 대 한 이름을 지정할 수 있습니다. DSN 이름이 예: Excel 파일에 대 한.xls 또는.mdb 파일 액세스에 대 한 적절 한 파일 확장명으로 끝나는 있는지 확인 해야 합니다.  
  
     Dsn에 대 한 자세한 내용은 참조 하십시오. [파일 데이터 원본을](https://msdn.microsoft.com/library/ms715401.aspx) ODBC sdk에서입니다.  
  
-   **데이터 원본 컴퓨터** 탭:이 탭에는 시스템 및 사용자 데이터 원본을 나열 합니다. 사용자 데이터 원본은이 컴퓨터에서 사용자에 게 적용 됩니다. 시스템 데이터 원본 또는 시스템 전체 서비스에이 컴퓨터에서 모든 사용자가 사용할 수 있습니다. 참조 [데이터 소스 컴퓨터](https://msdn.microsoft.com/library/ms710952.aspx) ODBC sdk  
  
 ODBC 데이터 원본에 대 한 자세한 내용은 참조 하십시오. [데이터 원본](https://msdn.microsoft.com/library/ms711688.aspx) ODBC sdk에서입니다.  
  
 클릭 **확인** 를 완료 합니다. **데이터베이스 개체 선택** 대화 상자가 나타납니다. 이 대화 상자에서 테이블을 선택 하거나 소비자가 사용할 보고 합니다. 참고 항목을 클릭 하는 동안 컨트롤이 키를 누른 상태 뷰와 테이블을 여러 개 선택할 수 있습니다.  
  
 **클래스**  
 기본적으로 이름을 기반으로 선택한 파일 또는 컴퓨터 데이터 원본의 소비자 클래스의 이름입니다.  
  
 **.h 파일**  
 선택한 파일 또는 컴퓨터 데이터 원본 이름이 기본적으로 하는 소비자 클래스 헤더 파일의 이름입니다.  
  
 **.cpp 파일**  
 선택한 파일 또는 컴퓨터 데이터 원본 이름이 기본적으로 하는 소비자 클래스 구현 파일의 이름입니다.  
  
 **Type**  
 다이너셋 (기본값) 또는 스냅숏을 레코드 집합 인지 여부를 지정 합니다.  
  
-   **다이너셋**: 레코드 집합 다이너셋 임을 지정 합니다. 다이너셋 쿼리 된 데이터베이스의 데이터에 인덱싱된 뷰를 제공 하는 쿼리 결과입니다. 다이너셋은 캐싱하므로 원래 데이터에 정수 인덱스만 및 스냅숏에 대 한 성능이 향상 됩니다. 각 레코드에 직접 인덱스 지점 쿼리 결과로 검색 및 레코드가 제거 되는 경우를 나타냅니다. 또한 업데이트 된 정보에 액세스할 쿼리 한 레코드의 수 있습니다. 이 값이 기본값입니다.  
  
-   **스냅숏**: 레코드 집합이 스냅숏 임을 지정 합니다. 스냅숏으로 쿼리의 결과 이므로 특정 시점의 데이터베이스에 대 한 뷰. 원본 레코드에 변경 내용을 표시 되지 않으면 하므로 쿼리의 결과로 검색 된 모든 레코드가 캐시 됩니다.  
  
 **모든 열 바인딩**  
 선택한 테이블의 모든 열은 바인딩되어 있는지 여부를 지정 합니다. (기본값)이이 상자를 선택 하면 모든 열이 바인딩됩니다. 이 상자를 선택 하지 않으면 열이 없습니다, 바인딩되며 레코드 집합 클래스에 수동으로 바인딩해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ODBC 소비](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)

