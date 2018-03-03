---
title: "ODBC 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.data
dev_langs:
- C++
helpviewer_keywords:
- database classes [MFC], ODBC
- ODBC classes [MFC]
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33fcc3453d36a2567330f60cec73383f842210c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-classes"></a>ODBC 클래스
이러한 클래스는 다양 한 데이터베이스 ODBC (Open Connectivity) 드라이버를 사용할 수 있는 데이터베이스에 쉽게 액세스할 수 있도록를 다른 응용 프로그램 프레임 워크 클래스와 함께 작동 합니다.  
  
 ODBC 데이터베이스를 사용 하는 프로그램은 최소한 `CDatabase` 개체 및 `CRecordset` 개체입니다.  
  
 [CDatabase](../mfc/reference/cdatabase-class.md)  
 데이터 원본에서 작동할 수 있는 데이터 원본에 대 한 연결을 캡슐화 합니다.  
  
 [CRecordset](../mfc/reference/crecordset-class.md)  
 데이터 소스에서 선택한 레코드 집합을 캡슐화 합니다. 레코드 집합 활성화 레코드 스크롤, (추가, 편집 및 삭제할 레코드) 레코드를 업데이트 하 고, 필터를 사용 하 여 선택 영역을 정하는 선택 항목을 정렬 한 가져오거나 런타임 시 계산 된 선택 정보로 매개 변수화 합니다.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 폼을 제공 recordset 개체에 직접 연결 된입니다. 대화 상자 데이터 교환 (DDX) 메커니즘의 레코드 집합 및 레코드 뷰 컨트롤 간의 데이터를 교환 합니다. 모든 폼 보기와 같은 레코드 뷰는 대화 상자 템플릿 리소스를 기반으로 합니다. 레코드 뷰는 또한 레코드 집합의 레코드 간을 이동 하 고 레코드를 업데이트할 레코드 보기를 닫으면 관련된 레코드 집합을 닫으면 지원 합니다.  
  
 [잠금](../mfc/reference/cdbexception-class.md)  
 처리 오류 데이터 액세스에서에서 발생 하는 예외입니다. 이 클래스는 클래스 라이브러리의 예외 처리 메커니즘에 다른 예외 클래스와 같은 용도로 사용 됩니다.  
  
 [CFieldExchange](../mfc/reference/cfieldexchange-class.md)  
 필드 데이터 멤버 및 매개 변수 데이터 멤버의 레코드 집합 개체와 데이터 원본에 해당 테이블 열 간의 데이터를 교환 하는 레코드 필드 교환 (RFX)를 지원 하기 위한 컨텍스트 정보를 제공 합니다. 클래스와 유사 합니다 [CDataExchange](../mfc/reference/cdataexchange-class.md), 대화 상자 데이터 교환 (DDX)에 마찬가지로 사용 됩니다.  
  
## <a name="related-classes"></a>관련된 클래스  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 비트맵과 같은 이진 큰 개체 (BLOB)에 대 한 저장소에 대 한 핸들을 캡슐화합니다. `CLongBinary`개체는 데이터베이스 테이블에 저장 된 큰 데이터 개체를 관리 하는 데 사용 됩니다.  
  
 [CDBVariant](../mfc/reference/cdbvariant-class.md)  
 값의 데이터 형식에 관계 없이 값을 저장할 수 있습니다. `CDBVariant`데이터 형식의 공용 구조체에 저장 된 현재 값을 추적 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

