---
title: "문서 및 뷰 정리 | Microsoft Docs"
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
  - "문서, 정리"
  - "문서, 닫기"
  - "뷰, 정리"
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 문서 및 뷰 정리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문서가 닫히는 중에 프레임 워크는 첫 번째로 [DeleteContents](../Topic/CDocument::DeleteContents.md) 멤버 함수를 호출합니다.  문서의 작업 과정에서 힙에 메모리를 할당하는 경우, `DeleteContents` 는 할당을 취소하기에 가장 좋은 곳입니다.  
  
> [!NOTE]
>  문서의 소멸자에서 문서 데이터 할당을 취소하지 않아야 합니다.  SDI 응용 프로그램의 경우 문서 개체를 다시 사용할 수도 있습니다.  
  
 힙에 할당 된 메모리 할당을 취소 하려면 뷰의 소멸자를 재정의할 수 있습니다.  
  
## 참고 항목  
 [문서 및 뷰 초기화 및 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)