---
title: "초기화 및 문서 및 뷰 정리 | Microsoft Docs"
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
- initializing documents [MFC]
- views [MFC], cleaning up
- documents [MFC], initializing
- documents [MFC], cleaning up
- views [MFC], initializing
- initializing objects [MFC], document objects
- document objects [MFC], life cycle of
- initializing views [MFC]
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0546bfc0a5226c6cd22497acae1bb364ceba107b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>문서 및 뷰 초기화 및 정리
초기화 하 고 문서 및 뷰 정리에 대 한 다음 지침을 따르세요.  
  
-   문서 및 뷰; MFC 프레임 워크를 초기화 합니다. 에 추가 하는 모든 데이터를 초기화 합니다.  
  
-   프레임 워크 문서로 정리 하 고 뷰를 닫습니다. 이러한 문서 및 뷰의 멤버 함수에서 힙에 할당 하는 모든 메모리 할당을 취소 해야 합니다.  
  
> [!NOTE]
>  재정의에서 가장 잘 이루어집니다 전체 응용 프로그램에 대 한 초기화를 회수는 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 클래스의 멤버 함수 `CWinApp`, 전체 응용 프로그램에 대 한 정리는 의재정의에서가장잘대상과`CWinApp`멤버 함수 [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance)합니다.  
  
 수명 주기의 문서 (및 해당 프레임 창 및 보기 또는 뷰)는 mdi에서 응용 프로그램은 다음과 같습니다.  
  
1.  동적를 만드는 동안 문서 생성자가 호출 됩니다.  
  
2.  각 새 문서, 문서에 대 한 [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) 또는 [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) 호출 됩니다.  
  
3.  사용자는 전체 수명 동안 문서와 상호 작용합니다. 일반적으로이 따라 선택 하 고 데이터를 편집 사용자 문서 데이터 보기를 통해 지속적으로 발생 합니다. 변경 내용을 저장 및 다른 뷰를 업데이트에 대 한 문서를 전달 하는 보기입니다. 이 시간 동안 문서와 보기 명령을 처리할 수도 있습니다.  
  
4.  프레임 워크를 호출 하 여 [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) 문서에 특정 데이터를 삭제 합니다.  
  
5.  문서의 소멸자가 호출 됩니다.  
  
 SDI 응용 프로그램에서 1 단계 문서 처음 만들 때 한 번 수행 됩니다. 그런 다음 2-4 단계 반복 하 여 수행 새 문서를 열 때마다 합니다. 새 문서는 기존 문서 개체를 다시 사용합니다. 마지막으로, 응용 프로그램이 종료 될 때 5 단계를 수행 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [문서 및 뷰 초기화](../mfc/initializing-documents-and-views.md)  
  
-   [문서 및 뷰 정리](../mfc/cleaning-up-documents-and-views.md)  
  
## <a name="see-also"></a>참고 항목  
 [문서/뷰 아키텍처](../mfc/document-view-architecture.md)

