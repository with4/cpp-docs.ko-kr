---
title: -/ / 생성자 주석 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f58c8410de51a4692dd0e7f018d40eaa28c0dae8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929584"
---
# <a name="-constructors-comment"></a>// 생성자 주석
`// Constructors` MFC 클래스 선언의 섹션으로 생성자 (c + + 의미에서)은 개체 사용 하는 데 필요한 초기화 함수를 선언 합니다. 예를 들어 `CWnd::Create` 는 사용 하기 전에 때문에 생성자 섹션에는 `CWnd` 개체 것 생성 해야 합니다"완전히" c + + 생성자를 호출 하는 먼저 호출한 다음 여는 `Create` 함수입니다. 일반적으로 이러한 멤버는 public입니다.  
  
 예를 들어 클래스 `CStdioFile` 중 하나는 아래의 목록에 표시 되는 세 가지 생성자가 [주석 예는](../mfc/an-example-of-the-comments.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 소스 파일을 사용 하 여](../mfc/using-the-mfc-source-files.md)   
 [/ / 구현 주석](../mfc/decrement-implementation-comment.md)   
 [/ / 특성 주석](../mfc/decrement-attributes-comment.md)   
 [/ / 작업 주석](../mfc/decrement-operations-comment.md)   
 [/ / 재정의 가능 주석](../mfc/decrement-overridables-comment.md)

