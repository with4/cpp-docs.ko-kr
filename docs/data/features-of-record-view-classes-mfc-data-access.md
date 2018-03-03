---
title: "레코드의 기능 볼 클래스 (MFC 데이터 액세스) | Microsoft Docs"
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
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c975aac0459a13a3fb95fdec3dff1a648b0efec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>레코드 뷰 클래스의 기능  (MFC Data Access)
클래스와 함께 양식 기반 데이터 액세스 프로그래밍을 수행할 수 [CFormView](../mfc/reference/cformview-class.md), 하지만 [CRecordView](../mfc/reference/crecordview-class.md) 는 일반적으로 더 나은 클래스에서 파생 되도록 합니다. 외에 해당 `CFormView` 기능 `CRecordView`:  
  
-   폼 컨트롤과 관련된 레코드 집합 개체 간에 대화 상자 데이터 교환 (DDX)를 제공합니다.  
  
-   관련된 레코드 집합 개체의 레코드를 탐색할 수 있도록 처음으로 이동, 다음으로 이동, 이전 이동 및 마지막으로 이동 명령을 처리 합니다.  
  
-   사용자가 다른 레코드로 이동할 때 현재 레코드에 변경 내용을 업데이트 합니다.  
  
 탐색에 대 한 자세한 내용은 참조 [레코드 뷰: 레코드 뷰에서의 탐색 지원](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 뷰 (데이터 액세스)](../data/record-views-mfc-data-access.md)   
 [ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)