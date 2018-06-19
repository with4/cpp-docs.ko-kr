---
title: 속성 시트 및 속성 페이지 (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], tabs
- property pages [MFC], property sheets
- CPropertyPage class [MFC], property sheets and pages
- CPropertySheet class [MFC], property sheets and pages
- property sheets, propert pages
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 882b2d93ba7938017f64b1ad8fb8e680e0af42db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348991"
---
# <a name="property-sheets-and-property-pages-mfc"></a>속성 시트 및 속성 페이지(MFC)
MFC [대화 상자](../mfc/dialog-boxes.md) 속성 시트 및 속성 페이지를 통합 하 여 "탭 대화 상자" 모양에 대해 수행할 수 있습니다. 이런이 종류의 대화 상자, Microsoft Word, Excel 및 Visual c + +의 여러 대화 상자와 유사한 "속성 시트" MFC에서 호출 스택을 앞에서 뒤로, 또는 계단식된 창 그룹에서 보이는 파일 폴더는 스택 매우 유사 하 게 탭 시트 포함 나타납니다. 전면 탭 컨트롤은 볼 수 있습니다. 레이블이 지정 된 탭만 후면 탭에 표시 됩니다. 속성 시트는 많은 수의 속성이 나 여러 그룹에 속하는 설정을 관리 하는 데 특히 유용 합니다. 일반적으로 하나의 속성 시트는 여러 개별 대화 상자를 대체 하 여 사용자 인터페이스를 단순화할 수 있습니다.  
  
 MFC 버전 4.0부터 속성 시트 및 속성 페이지 구현 Windows 95 및 Windows NT 버전 3.51 이상에서 제공 하는 공용 컨트롤을 사용 하 여 합니다.  
  
 속성 시트 클래스를 사용 하 여 구현 됩니다 [CPropertySheet](../mfc/reference/cpropertysheet-class.md) 및 [CPropertyPage](../mfc/reference/cpropertypage-class.md) (에 설명 된 *MFC 참조*). `CPropertySheet` 여러 "페이지"에 따라 포함할 수 있는 전체 대화 상자에서 정의 `CPropertyPage`합니다.  
  
 속성 시트를 만들고 작업에 대 한 내용은 항목을 참조 [속성 시트](../mfc/property-sheets-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)   
 [속성 시트 및 MFC의 속성 페이지](../mfc/property-sheets-and-property-pages-in-mfc.md)   
 [데이터 교환](../mfc/exchanging-data.md)   
 [모덜리스 속성 시트 만들기](../mfc/creating-a-modeless-property-sheet.md)   
 [적용 단추 처리](../mfc/handling-the-apply-button.md)

