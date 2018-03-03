---
title: "속성 시트 및 MFC의 속성 페이지 | Microsoft Docs"
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
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24a66bf9e062e43225827afdbb0bba45511c5f13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC의 속성 시트 및 속성 페이지
으로 알려진 탭 대화 상자는 속성 시트는 속성 페이지를 포함 하는 대화 상자. 각 속성 페이지 대화 상자 템플릿 리소스를 기반으로 하며 컨트롤을 포함 합니다. 위에 표시 탭 된 페이지에 묶여 있습니다. 탭은 페이지에 이름을 지정 하 고 용도 나타냅니다. 사용자가 컨트롤의 집합을 선택 하 고 속성 시트에 탭을 클릭 합니다.  
  
 페이지를 사용 하 여 의미 있는 집합으로 속성 시트에 컨트롤을 그룹화 합니다. 포함 된 속성 시트에는 일반적으로 자체의 여러 컨트롤에 있습니다. 이러한 모든 페이지에 적용 합니다.  
  
 클래스를 기반으로 하는 속성 시트 [CPropertySheet](../mfc/reference/cpropertysheet-class.md)합니다. 클래스를 기반으로 하는 속성 페이지 [CPropertyPage](../mfc/reference/cpropertypage-class.md)합니다.  
  
 속성 시트에는 일반적으로 보기에서 현재 선택과 같은 일부 외부 개체의 속성을 수정 하는 데 사용 되는 대화 상자의 특별 한 종류입니다. 속성 시트에 세 개의 주요 부분: 한 번에 하나씩 표시 되 고 해당 페이지를 선택 하려면 사용자가 클릭 하는 각 페이지 맨 위에 있는 탭을 포함 하는 대화 상자, 하나 이상의 속성 페이지. 속성 시트는 설정 또는 변경 하는 옵션의 몇 가지 유사한 그룹 있는 경우 유용 합니다. 속성 시트를 이해 하기 쉬운 방식으로 정보를 그룹화합니다.  
  
> [!NOTE]
>  속성 시트를 사용 하 여 표시 하려는 경우 `CPropertySheet::DoModal`, 시스템 첫째 예외를 생성할 수 있습니다. 이 예외는 시스템 변경 하려고 하기 때문에 발생는 [창 스타일](../mfc/reference/styles-used-by-mfc.md#window-styles) 개체가 생성 되기 전에 개체의 합니다. 이 예외와 방지 하거나 처리 하는 방법에 대 한 자세한 내용은 참조 [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 시트](../mfc/property-sheets-mfc.md)

