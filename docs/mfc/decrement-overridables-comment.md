---
title: -재정의 가능 주석 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Overridables comment in MFC source files
- MFC source files, Overridables comment
- overriding, Overridables comment in MFC source files
- comments, MFC
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b71d61175e5446ac33dd0ff6a011d06f601b5a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-overridables-comment"></a>// 재정의 가능 주석
`// Overridables` MFC 클래스 선언의 섹션 가상 함수가 포함 된 기본 클래스의 동작을 수정 해야 하는 경우 파생된 클래스에서 재정의할 수 있습니다. 일반적으로 이름으로 지정 된 "On"로 시작 하지만 꼭 필요 하지 않음. 여기에서 함수는 재정의할 수 종종 구현 하거나 어떤 종류의 "callback" 또는 "후크"를 제공 하도록 설계 되었습니다. 일반적으로 이러한 구성원 보호 됩니다.  
  
 MFC에서 순수 가상 함수는 항상이 섹션에 배치 됩니다. C + +의 순수 가상 함수 형식 중 하나입니다.  
  
 `virtual void OnDraw( ) = 0;`  
  
 클래스를 나열 하는 샘플에서 `CStdioFile`에 [주석 예는](../mfc/an-example-of-the-comments.md), / / 재정의 가능 섹션이 없습니다.이 목록에 포함 됩니다. 클래스 **CDocument**, 반면에 약 10 재정의 가능한 멤버 함수를 나열 합니다.  
  
 일부 클래스에도 표시 주석 `// Advanced Overridables`합니다. 이것은 고급만 함수 프로그래머를 재정의 하려고 해야 합니다. 하지 않을 재정의 해야 합니다.  
  
> [!NOTE]
>  이 문서에 설명 된 규칙도 잘 일반적으로 자동화 (이전의 OLE 자동화) 메서드 및 속성에 대 한 합니다. 자동화 메서드는 MFC 작업과 비슷합니다. 자동화 속성은 MFC 특성 유사 합니다. 자동화 이벤트 (이전의 OLE 컨트롤의 ActiveX 컨트롤에 대 한 지원)는 MFC 재정의 가능 멤버 함수와 비슷합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 소스 파일을 사용 하 여](../mfc/using-the-mfc-source-files.md)   
 [주석 예](../mfc/an-example-of-the-comments.md)   
 [/ / 구현 주석](../mfc/decrement-implementation-comment.md)   
 [/ / 생성자 주석](../mfc/decrement-constructors-comment.md)   
 [/ / 특성 주석](../mfc/decrement-attributes-comment.md)   
 [/ / 작업 주석](../mfc/decrement-operations-comment.md)

