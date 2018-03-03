---
title: "문서 및 뷰 정리 | Microsoft Docs"
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
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a95193d5ca3df890c9c97f458b76413e588bc59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cleaning-up-documents-and-views"></a>문서 및 뷰 정리
프레임 워크를 먼저 호출 문서를 닫을 때 해당 [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) 멤버 함수입니다. 문서 작업 중 힙에서 메모리를 할당한 경우 메모리를 할당 해제하기에 가장 좋은 위치는 `DeleteContents`입니다.  
  
> [!NOTE]
>  문서의 소멸자에서는 문서 데이터를 할당 해제하지 않아야 합니다. SDI 응용 프로그램의 경우 문서 개체를 다시 사용할 수 있습니다.  
  
 힙에 할당한 메모리를 할당 해제하도록 뷰의 소멸자를 재정의할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 및 뷰 초기화 및 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)

