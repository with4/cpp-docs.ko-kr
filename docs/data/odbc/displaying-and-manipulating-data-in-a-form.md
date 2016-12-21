---
title: "폼에서 데이터의 표시와 조작 | Microsoft Docs"
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
  - "데이터[MFC]"
  - "데이터[MFC], 폼에서 표시"
  - "데이터 표시[C++], 폼"
  - "폼[C++], 데이터 표시"
  - "ODBC[C++], 폼"
  - "레코드 뷰[C++], 데이터 표시"
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 폼에서 데이터의 표시와 조작
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

많은 데이터 액세스 응용 프로그램은 폼의 필드를 이용하여 데이터를 선택하고 표시합니다.  [CRecordView](../../mfc/reference/crecordview-class.md) 데이터베이스 클래스는 레코드 집합 개체에 직접 연결되는 [CFormView](../../mfc/reference/cformview-class.md) 개체를 제공합니다.  레코드 뷰는 [DDX\(대화 상자 데이터 교환\)](../../mfc/dialog-data-exchange-and-validation.md)를 사용하여 레코드 집합에 있는 현재 레코드의 필드 값을 폼의 컨트롤로 이동시키고 업데이트된 정보를 다시 레코드 집합으로 이동시킵니다.  그런 다음 레코드 집합은 RFX\(레코드 필드 교환\)를 사용하여 자체 필드 데이터 멤버와 데이터 소스에 있는 테이블의 해당 열 사이로 데이터를 이동시킵니다.  
  
 MFC 응용 프로그램 마법사나 **클래스 추가**\([MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)의 설명 참조\)를 사용하여 뷰 클래스 및 여기에 연결되는 레코드 집합 클래스를 동시에 만들 수 있습니다.  
  
 레코드 뷰 및 해당 레코드 집합은 문서를 닫을 때 삭제됩니다.  레코드 뷰에 대한 자세한 내용은 [레코드 뷰](../../data/record-views-mfc-data-access.md)를 참조하십시오.  RFX\(레코드 필드 교환\)에 대한 자세한 내용은 [RFX](../../data/odbc/record-field-exchange-rfx.md)를 참조하십시오.  
  
## 참고 항목  
 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)