---
title: "이미지 목록 조작 | Microsoft Docs"
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
  - "CImageList 클래스, 조작"
  - "이미지 목록[C++], 조작"
  - "목록[C++], 이미지"
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 이미지 목록 조작
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Replace](../Topic/CImageList::Replace.md) 멤버 함수는 이미지 목록에서\([CImageList](../mfc/reference/cimagelist-class.md)\) 이미지를 새 이미지로 대체합니다.  또한 이 기능은 동적으로 이미지 목록 개체에서 이미지 개수를 늘려야 할때 유용합니다.  [SetImageCount](../Topic/CImageList::SetImageCount.md) 함수는 동적으로 이미지 목록에 있는 이미지의 수를 변경합니다.  이미지 목록의 크기를 늘리는 경우, **Replace**  를 호출하여 새 이미지 슬롯에 이미지를 추가하십시오.  이미지 목록의 크기를 줄이려면 이미지는 해제 된 새 크기를 넘어야 합니다.  
  
 [Remove](../Topic/CImageList::Remove.md) 멤버 함수는 이미지 목록에서 이미지를 제거합니다.  [Copy](../Topic/CImageList::Copy.md) 멤버 함수는 이미지 목록에서 이미지를 복사하거나 스왑할 수 있습니다.  이 기능을 사용 하면 원본 이미지를 대상 인덱스로 복사하거나 또는 소스 및 대상 이미지를 바꾸어야 하는지 여부를 나타낼 수 있습니다.  
  
 두 개의 이미지 목록을 병합하여 새 이미지 목록을 만들려는 경우, [Create](../Topic/CImageList::Create.md) 멤버 함수의 적절한 오버로드를 사용하십시오.  **Create** 의 오버로드는 기존 이미지 목록의 첫 번째 이미지를 새 이미지 목록 개체의 결과 이미지로 저장하여 병합합니다.   새 이미지는 두 번째 이미지는 첫 번째 이미지에 투명하게 그려서 만들어 집니다.  새 이미지에 대한 마스크는 두 기존 이미지의 마스크 비트에 논리적 OR 연산을 수행 합니다.  
  
 이 모든 이미지가 병합 되어 새 이미지 목록 개체에 추가 될 때까지 반복 됩니다.  
  
 [Write](../Topic/CImageList::Write.md) 멤버 함수를 호출하여 아카이브 하기 위해 이미지 정보를 쓸 수 있으며, [Read](../Topic/CImageList::Read.md) 멤버 함수를 호출하여 이 것을 다시 읽을 수 있습니다.  
  
 [GetSafeHandle](../Topic/CImageList::GetSafeHandle.md), [Attach](../Topic/CImageList::Attach.md), 및 [Detach](../Topic/CImageList::Detach.md) 멤버 함수는 [DeleteImageList](../Topic/CImageList::DeleteImageList.md) 멤버 함수가 `CImageList` 개체를 제거하지 않고 이미지 목록을 제거할 때 `CImageList` 개체에 연결된 이미지 목록의 처리기를 조작할 수 있도록 허용합니다.  
  
## 참고 항목  
 [CImageList 사용](../mfc/using-cimagelist.md)   
 [컨트롤](../mfc/controls-mfc.md)