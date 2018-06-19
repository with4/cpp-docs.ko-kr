---
title: MFC를 사용 하 여 소스 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- public members
- source files
- MFC, source files
- MFC source files
- comments, MFC
- private member access
- protected member access
- source files, MFC
ms.assetid: 3230e8fb-3b69-4ddf-9538-365ac7ea5e72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73177d8b73d5f4be6d886b0bda84f1e1241488cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384337"
---
# <a name="using-the-mfc-source-files"></a>MFC 소스 파일 사용
Microsoft Foundation 클래스 (MFC) 라이브러리는 전체 소스 코드를 제공합니다. 헤더 파일 (.h) \atlmfc\include 디렉터리;에 구현 파일 (.cpp)가 \atlmfc\src\mfc 디렉터리에 있습니다.  
  
 문서이에서는 MFC를 사용 하 여 각 클래스의 다양 한 부분, 이러한 의견을 의미 하 고 각 섹션의 내용에 맞게 하시면 주석 처리 규칙에 설명 합니다. Visual c + + 마법사, 작성 하는 클래스에 대 한 유사한 규칙을 사용 하 고 보면 이러한 규칙 유용한 사용자 고유의 코드에 대 한 합니다.  
  
 에 대해 잘 알고 수도 있습니다는 **공용**, `protected`, 및 `private` c + + 키워드입니다. MFC 헤더 파일을 보면 각 클래스 각각의 여러 개 있을 수 있는지 알 수 있습니다. 예를 들어 public 멤버 변수와 함수 수 있습니다 하나 이상 **공용** 키워드입니다. 멤버 변수 및 함수를 허용 되는 액세스 유형별이 아닌 사용 용도에 따라 MFC 구분 하기 때문입니다. MFC 사용 하 여 `private` 엄밀한; 항목을 포함 구현 세부 사항을 일반적으로 보호 기능을 여러 번은 공용으로 간주 합니다. 구현 세부 정보에 대 한 액세스는 권장 되지 않지만 MFC가 결정 하도록 있습니다.  
  
 MFC 소스 파일 및 MFC 응용 프로그램 마법사에서 생성 하는 파일에서는 (일반적으로이 순서) 대로 클래스 선언 내에서 이러한 의견을 찾을 수 있습니다.  
  
 `// Constructors`  
  
 `// Attributes`  
  
 `// Operations`  
  
 `// Overridables`  
  
 `// Implementation`  
  
 다음이의 문서에서 다루는 항목은 다음과 같습니다.  
  
-   [주석 예](../mfc/an-example-of-the-comments.md)  
  
-   [/ / 구현 주석](../mfc/decrement-implementation-comment.md)  
  
-   [/ / 생성자 주석](../mfc/decrement-constructors-comment.md)  
  
-   [/ 특성 주석](../mfc/decrement-attributes-comment.md)  
  
-   [/ / 작업 주석](../mfc/decrement-operations-comment.md)  
  
-   [/ / / / 재정의 가능 주석](../mfc/decrement-overridables-comment.md)  
  
## <a name="see-also"></a>참고 항목  
 [일반 MFC 항목](../mfc/general-mfc-topics.md)

