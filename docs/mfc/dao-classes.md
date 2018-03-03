---
title: "DAO 클래스 | Microsoft Docs"
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
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c80351071318b88956fa3717875561bdf30232dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dao-classes"></a>DAO 클래스
이러한 클래스는 Microsoft Visual Basic 및 Microsoft Access와 같은 데이터베이스 엔진을 사용 하 여 개체 DAO (Data Access) 데이터베이스에 쉽게 액세스할 수 있도록를 다른 응용 프로그램 프레임 워크 클래스와 함께 작동 합니다. DAO 클래스의 다양 한 데이터베이스 ODBC (Open Connectivity) 드라이버를 사용할 수 있는 데이터베이스 액세스할 수도 있습니다.  
  
 DAO 데이터베이스를 사용 하는 프로그램은 최소한 `CDaoDatabase` 개체 및 `CDaoRecordset` 개체입니다.  
  
> [!NOTE]
>  Visual c + + 환경 및 마법사 더 이상 지원 DAO (하지만 DAO 클래스에 포함 되어 있으며 계속 사용할 수 없습니다). 새 MFC 프로젝트에 대 한 ODBC를 사용 하는 것이 좋습니다. DAO는 기존 응용 프로그램 유지 관리만 사용할 수 있습니다.  
  
 [CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)  
 부터 로그인까지에서 된 명명 된 암호로 보호 된 데이터베이스 세션을 관리합니다. 대부분의 프로그램의 기본 작업 영역을 사용 합니다.  
  
 [CDaoDatabase](../mfc/reference/cdaodatabase-class.md)  
 데이터에서 작동할 수 있는 데이터베이스에 연결 합니다.  
  
 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)  
 데이터 소스에서 선택한 레코드 집합을 나타냅니다.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 컨트롤에 데이터베이스 레코드를 표시하는 뷰입니다.  
  
 [CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)  
 일반적으로 하나는 데이터베이스에 저장 된 쿼리 정의 나타냅니다.  
  
 [CDaoTableDef](../mfc/reference/cdaotabledef-class.md)  
 기본 테이블 또는 연결된 테이블의 저장된 정의를 나타냅니다.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 DAO 클래스에서 발생 하는 예외 상태를 나타냅니다.  
  
 [CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)  
 DAO 데이터베이스 클래스에서 사용하는 DAO 레코드 필드 교환(DFX) 루틴을 지원합니다. 이 클래스가 직접 사용 되지 않습니다 됩니다.  
  
## <a name="related-classes"></a>관련된 클래스  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 비트맵과 같은 이진 큰 개체 (BLOB)에 대 한 저장소에 대 한 핸들을 캡슐화합니다. `CLongBinary`개체는 데이터베이스 테이블에 저장 된 큰 데이터 개체를 관리 하는 데 사용 됩니다.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 OLE 자동화 형식에 대 한 래퍼 **통화**, 소수점 앞에 15 자릿수와 뒤에 4 자릿수 고정 소수점 산술 형식인 합니다.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 OLE 자동화 형식에 대 한 래퍼 **날짜**합니다. 날짜 및 시간 값을 나타냅니다.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 OLE 자동화 형식에 대 한 래퍼 **VARIANT**합니다. 데이터에 **VARIANT**형식으로 저장할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

