---
title: "머리글 및 바닥글 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- printing [MFC], multipage documents
- page headers [MFC], printing
- headers [MFC], printing
- footers [MFC], printing
- page footers [MFC], printing
- page headers [MFC]
- printing [MFC], headers and footers
- page footers [MFC]
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7525cba7d05c4d04f0548bd2dc774503b284c220
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="headers-and-footers"></a>머리글 및 바닥글
이 문서에서는 인쇄 문서에 머리글 및 바닥글을 추가 하는 방법에 설명 합니다.  
  
 화면에 문서를 볼 때 문서 및 문서의 현재 위치 이름 일반적으로 제목 표시줄 및 상태 표시줄에 표시 됩니다. 문서의 인쇄 된 복사본을 보면 머리글 또는 바닥글에 표시 된 이름 및 페이지 번호가 유용 합니다. 이 어떤도 wysiwyg에서 프로그램 다 인쇄와 화면 표시를 수행 하는 방법에 일반적인 방법입니다.  
  
 [OnPrint](../mfc/reference/cview-class.md#onprint) 멤버 함수는 각 페이지에 대 한 호출 되기 때문에 및 화면 디스플레이 대 한 인쇄에 대해서만 호출 되기 때문에 머리글이 나 바닥글을 인쇄 하려면 적절 한 위치입니다. 머리글 또는 바닥글을 인쇄 하는 별도 함수를 정의 하 고 프린터 장치 컨텍스트를 전달할 수 `OnPrint`합니다. 원본 창 또는 호출 하기 전에 범위를 조정 해야 할 수 있습니다 [OnDraw](../mfc/reference/cview-class.md#ondraw) 페이지 겹치는 머리글 또는 바닥글의 본문 되지 않도록 합니다. 수정 해야 할 수 있습니다 `OnDraw` 페이지에 들어가는 문서의 양을 줄일 수 때문에 있습니다.  
  
 머리글 또는 바닥글을 수행한 영역 사용 하는 것에 대 한 보정 하는 한 가지 방법은 **m_rectDraw** 소속 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)합니다. 페이지 인쇄 될 때마다가이 멤버는 사용 가능한 페이지 영역으로 초기화 됩니다. 페이지의 본문을 인쇄 하기 전에 머리글 또는 바닥글을 인쇄 하는 경우에 저장 된 사각형의 크기를 줄일 수 있습니다 **m_rectDraw** 머리글 또는 바닥글을 수행한 영역을 설명 하기 위해 합니다. 다음 `OnPrint` 를 참조할 수 **m_rectDraw** 인쇄 페이지의 본문에 대해 남아 있는 양을 영역 찾으려고 합니다.  
  
 헤더 또는 다른에서 인쇄할 수 없는 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc)하기 전에 호출 되어는 `StartPage` 의 멤버 함수 [CDC](../mfc/reference/cdc-class.md) 가 호출 합니다. 이 시점에서 프린터 장치 컨텍스트는 페이지 경계에 있을으로 간주 됩니다. 에서만 인쇄를 수행할 수 있습니다는 `OnPrint` 멤버 함수입니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [다중 페이지 문서 인쇄](../mfc/multipage-documents.md)  
  
-   [인쇄를 위한 GDI 리소스 할당](../mfc/allocating-gdi-resources.md)  
  
## <a name="see-also"></a>참고 항목  
 [인쇄](../mfc/printing.md)

