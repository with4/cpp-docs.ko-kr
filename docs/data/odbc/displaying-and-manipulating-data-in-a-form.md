---
title: "폼에 데이터 표시 및 조작 | Microsoft Docs"
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
- forms [C++], displaying data
- displaying data [C++], forms
- ODBC [C++], forms
- record views [C++], displaying data
- data [MFC]
- data [MFC], displaying in a form
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1a7960780f1f83833e25c9a094a36314a299a042
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="displaying-and-manipulating-data-in-a-form"></a>폼에서 데이터의 표시와 조작
여러 데이터 액세스 응용 프로그램 데이터를 선택 하 고 폼의 필드에 표시 합니다. 데이터베이스 클래스 [CRecordView](../../mfc/reference/crecordview-class.md) 제공는 [CFormView](../../mfc/reference/cformview-class.md) recordset 개체에 직접 연결 하는 개체입니다. 레코드 뷰 사용 하 여 [대화 상자 데이터 교환 (DDX)](../../mfc/dialog-data-exchange-and-validation.md) 폼에서 컨트롤을 레코드 집합에서 현재 레코드의 필드의 값을 이동 하 고 레코드 집합에 업데이트 된 정보를 다시 이동할 수 있습니다. 레코드 집합은 레코드 필드 교환 (RFX)를 사용 하 여 데이터 원본에서의 필드 데이터 멤버와 테이블의 해당 열 데이터를 이동 시킵니다.  
  
 MFC 응용 프로그램 마법사를 사용할 수 있습니다 또는 **클래스 추가** (에 설명 된 대로 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) 함께에서 뷰 클래스와 연결 된 레코드 집합 클래스를 만들려고 합니다.  
  
 레코드 뷰 및 해당 레코드 집합 문서를 닫을 때 삭제 됩니다. 레코드 뷰에 대 한 자세한 내용은 참조 [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다. RFX에 대 한 자세한 내용은 참조 [Exchange RFX (레코드 필드)](../../data/odbc/record-field-exchange-rfx.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)