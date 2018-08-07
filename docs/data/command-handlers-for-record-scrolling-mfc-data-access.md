---
title: 레코드 스크롤 (MFC Data Access)에 대 한 처리기를 명령 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ef2b57bd37441b9a35c26ab36fcf3cb15cd0d878
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340330"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>레코드 스크롤에 대한 명령 처리기  (MFC Data Access)
합니다 [CRecordView](../mfc/reference/crecordview-class.md) 클래스는 기본 명령에는 다음 표준 명령에 대 한 처리를 제공 합니다.  
  
-   ID_RECORD_MOVE_FIRST  
  
-   ID_RECORD_MOVE_LAST  
  
-   ID_RECORD_MOVE_NEXT  
  
-   ID_RECORD_MOVE_PREV  
  
 `OnMove` 멤버 함수는 기본 명령 이동할 레코드에 있는 모든 네 가지 명령에 대 한 처리를 제공 합니다. 이러한 명령을 실행하면 RFX 또는 DFX는 새 레코드를 레코드 집합의 필드에 로드하고 DDX는 레코드 폼의 컨트롤로 값을 이동합니다. RFX에 대 한 정보를 참조 하세요 [Exchange RFX (레코드 필드)](../data/odbc/record-field-exchange-rfx.md)합니다.  
  
> [!NOTE]
>  표준 레코드 탐색 명령과 연결된 모든 사용자 인터페이스 개체에 대해 이러한 표준 명령 ID를 사용해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 뷰에서의 탐색 지원](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)