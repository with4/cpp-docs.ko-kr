---
title: "-/ / 구현 주석 | Microsoft Docs"
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
- Implementation comment in MFC source files
- comments, MFC
- MFC source files, Implementation comment
- comments, Implementation comments
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 437b091b2237c7219a0afeee46d78164751e6d3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="-implementation-comment"></a>// 구현 주석
`// Implementation` 섹션 모든 MFC 클래스 선언의 가장 중요 한 부분입니다.  
  
 이 섹션에는 모든 구현 정보가 있습니다. 멤버 변수와 멤버 함수는이 섹션에 나타날 수 있습니다. 이 줄 아래에 모든 것은 MFC의 이후 릴리스에서 변경할 수 있습니다. 아래 세부 정보에 의존 하지 해야 것을 피할 수 없는 경우가 아니면는 `// Implementation` 선입니다. 또한 일부 구현 기술 참고 사항에 대해서는 설명 하지만 아래 선언 된 멤버는 문서화 되지 않습니다. 기본 클래스의 가상 함수 재정의 섹션에 관계 없이 기본 클래스 함수에 정의 되어, 기본 클래스 구현을 재정의 팩트는 구현 정보 것 간주 되므로이 섹션에 있어야 합니다. 일반적으로 이러한 멤버 보호 되는 경우가 있습니다.  
  
 확인할 수는 `CStdioFile` 아래 나열 [주석 예는](../mfc/an-example-of-the-comments.md) 아래 선언 된 멤버는 `// Implementation` 주석으로 선언할 수 **공용**, `protected`, 또는 `private`. 만 나중에 변경 될 수 있으므로 주의 해야 이러한 멤버를 사용 해야 합니다. 선언으로 멤버 그룹 **공용** 제대로 작동 하려면 클래스 라이브러리 구현에 사용할 수 있습니다. 그러나 안전 하 게 선언 된 멤버를 사용할 수 있는이 아닙니다.  
  
> [!NOTE]
>  위 또는 아래 나머지 형식 주석을 사용할 수 있습니다는 `// Implementation` 메모 합니다. 두 경우 모두 아래 선언 된 멤버 종류 설명 합니다. 아래에 있는 경우는 `// Implementation` 주석 멤버 변경 될 수 있다는 이후 버전의 MFC 가정해 야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 소스 파일을 사용 하 여](../mfc/using-the-mfc-source-files.md)   
 [주석 예](../mfc/an-example-of-the-comments.md)   
 [/ / 생성자 주석](../mfc/decrement-constructors-comment.md)   
 [/ / 특성 주석](../mfc/decrement-attributes-comment.md)   
 [/ / 작업 주석](../mfc/decrement-operations-comment.md)   
 [/ / 재정의 가능 주석](../mfc/decrement-overridables-comment.md)

