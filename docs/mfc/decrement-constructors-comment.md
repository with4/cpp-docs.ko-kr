---
title: "-/ / 생성자 주석 | Microsoft Docs"
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
- constructors comment
- declarations, constructors
- MFC source files, Constructors comment
- declaring constructors, code comments
- comments, MFC
- comments, constructors comment
- constructors [MFC], declaring
- instance constructors, code comments
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f6425252df34936d4ba3c9013664205b0038d82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="-constructors-comment"></a>// 생성자 주석
`// Constructors` MFC 클래스 선언의 섹션으로 생성자 (c + + 의미에서)은 개체 사용 하는 데 필요한 초기화 함수를 선언 합니다. 예를 들어 `CWnd::Create` 는 사용 하기 전에 때문에 생성자 섹션에는 `CWnd` 개체 것 생성 해야 합니다"완전히" c + + 생성자를 호출 하는 먼저 호출한 다음 여는 **만들기** 함수입니다. 일반적으로 이러한 멤버는 public입니다.  
  
 예를 들어 클래스 `CStdioFile` 중 하나는 아래의 목록에 표시 되는 세 가지 생성자가 [주석 예는](../mfc/an-example-of-the-comments.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 소스 파일을 사용 하 여](../mfc/using-the-mfc-source-files.md)   
 [/ / 구현 주석](../mfc/decrement-implementation-comment.md)   
 [/ / 특성 주석](../mfc/decrement-attributes-comment.md)   
 [/ / 작업 주석](../mfc/decrement-operations-comment.md)   
 [/ / 재정의 가능 주석](../mfc/decrement-overridables-comment.md)

