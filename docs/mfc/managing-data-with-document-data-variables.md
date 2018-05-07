---
title: 문서 데이터 변수로 데이터 관리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8048a38c2ec09828c462d5b671cc0c89aec30805
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="managing-data-with-document-data-variables"></a>문서 데이터 변수로 데이터 관리
문서 클래스의 멤버 변수로 문서의 데이터를 구현 합니다. Scribble 프로그램 형식의 데이터 멤버를 선언 하는 예를 들어 `CObList` -에 대 한 포인터를 저장 하는 연결 된 목록 `CObject` 개체입니다. 이 목록은 자유 선 그리기를 구성 하는 점의 배열을 저장에 사용 됩니다.  
  
 문서의 멤버 데이터를 구현 하는 방법은 응용 프로그램의 특성에 따라 달라 집니다. 를 초과 하는 데 도움이 되도록 MFC 제공 "컬렉션 클래스" 들의 그룹-배열, 목록 및 맵 (사전) c + + 템플릿을 기반으로 하는 컬렉션을 포함 하 여-와 같은 다양 한 일반 데이터 형식 캡슐화 하는 클래스와 함께 `CString`, `CRect`, `CPoint`, `CSize`, 및 `CTime`합니다. 이러한 클래스에 대 한 자세한 내용은 참조는 [클래스 라이브러리 개요](../mfc/class-library-overview.md) 에 *MFC 참조*합니다.  
  
 문서의 멤버 데이터를 정의할 때 설정 하 고 데이터 항목을 가져올 다른 유용한 연산을 수행 하려면 문서 클래스에 멤버 함수 일반적으로 추가 합니다.  
  
 보기를 만들 때 보기에 설치 된 문서에 대 한 보기의 포인터를 사용 하 여 문서 개체에 액세스 합니다. 호출 하 여 보기의 멤버 함수에서이 포인터를 검색할 수 있습니다는 `CView` 멤버 함수 **GetDocument**합니다. 고유한 문서 형식에 대 한이 포인터를 캐스팅 해야 합니다. 다음 공용 문서 멤버 포인터를 통해 액세스할 수 있습니다.  
  
 데이터를 자주 전송에 직접 액세스 해야 문서 클래스의 public이 아닌 멤버를 사용 하려는 경우 뷰 friend (c + + 용어인) 문서 클래스의 클래스를 확인 하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 사용](../mfc/using-documents.md)

