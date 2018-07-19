---
title: 문서 및 뷰 정리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2dfe54c13db6f44bc70289380ae5f50d99c3722b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341328"
---
# <a name="cleaning-up-documents-and-views"></a>문서 및 뷰 정리
프레임 워크를 먼저 호출 문서를 닫을 때 해당 [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) 멤버 함수입니다. 문서 작업 중 힙에서 메모리를 할당한 경우 메모리를 할당 해제하기에 가장 좋은 위치는 `DeleteContents`입니다.  
  
> [!NOTE]
>  문서의 소멸자에서는 문서 데이터를 할당 해제하지 않아야 합니다. SDI 응용 프로그램의 경우 문서 개체를 다시 사용할 수 있습니다.  
  
 힙에 할당한 메모리를 할당 해제하도록 뷰의 소멸자를 재정의할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 및 뷰 초기화 및 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)

