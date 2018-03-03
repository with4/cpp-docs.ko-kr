---
title: "-특성 주석 | Microsoft Docs"
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
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18a142cc0434e0e09e69d9bffc30826c461cf185
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="-attributes-comment"></a>// 특성 주석
`// Attributes` MFC 클래스 선언의 섹션 개체의 공용 특성 (또는 속성)를 포함 합니다. 일반적으로 이러한 멤버 변수 또는 Get/Set 함수로 됩니다. "Get" 및 "Set" 함수 수도 있습니다 가상 되지 않을 수 있습니다. "Get" 함수는 일반적으로 **const**없기 때문에 대부분의 경우에서 이러한 의도 하지 않은, 합니다. 이러한 멤버는 일반적으로 공용; 일반적으로 보호 되 고 개인 특성 구현 섹션에 있습니다.  
  
 클래스를 나열 하는 샘플에서 `CStdioFile`아래 [주석 예는](../mfc/an-example-of-the-comments.md), 목록에 멤버 변수 하나가 포함 됩니다. `m_pStream`합니다. 클래스 `CDC` 이 주석은 아래의 약 20 명의 멤버를 나열 합니다.  
  
> [!NOTE]
>  와 같은 큰 클래스 `CDC` 및 `CWnd`, 너무 많은 멤버를 한 그룹에 있는 모든 특성을 나열 하는 단순히 더 쉽게 구별할 수 있도록 추가 있을 수 있습니다. 이 경우 클래스 라이브러리 머리글로 기타 주석을 멤버에 대 한 세부 사용. 예를 들어 `CDC` 사용 하 여 `// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions`, 등입니다. 특성을 나타내는 그룹을 위에서 설명한 하는 일반적인 구문이 될 예정입니다. 많은 OLE 클래스가 호출 하는 구현 섹션이 있는 `// Interface Maps`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 소스 파일을 사용 하 여](../mfc/using-the-mfc-source-files.md)   
 [주석 예](../mfc/an-example-of-the-comments.md)   
 [/ / 구현 주석](../mfc/decrement-implementation-comment.md)   
 [/ / 생성자 주석](../mfc/decrement-constructors-comment.md)   
 [/ / 작업 주석](../mfc/decrement-operations-comment.md)   
 [/ / 재정의 가능 주석](../mfc/decrement-overridables-comment.md)

