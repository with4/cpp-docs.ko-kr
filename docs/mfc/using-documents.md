---
title: 문서를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48f3bd6c6463bbbe26214a29960260d2be583e20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385640"
---
# <a name="using-documents"></a>문서 사용
문서 및 뷰를 함께 작동 합니다.  
  
-   포함, 관리 및 응용 프로그램별 표시 [데이터](../mfc/managing-data-with-document-data-variables.md)합니다.  
  
-   구성 된 인터페이스를 제공 [데이터 변수 문서](../mfc/managing-data-with-document-data-variables.md) 데이터를 조작 하기 위한 합니다.  
  
-   에 참여 [작성 하 고 파일을 읽는](../mfc/serializing-data-to-and-from-files.md)합니다.  
  
-   에 참여 [인쇄](../mfc/role-of-the-view-in-printing.md)합니다.  
  
-   [처리](../mfc/handling-commands-in-the-document.md) 대부분의 응용 프로그램의 명령 및 메시지입니다.  
  
 데이터 관리에 특히 관련 된 문서가 있습니다. 문서 클래스 멤버 변수에서 일반적으로 데이터를 저장 합니다. 보기 표시에 대 한 데이터를 액세스 하 고 업데이트할 이러한 변수를 사용 합니다. 문서의 기본 serialization 메커니즘 데이터 읽기 및 쓰기는 파일로 / 파일에서 관리 합니다. 문서를 처리할 수도 명령 (하지 Windows 이외의 다른 메시지 하지만 **WM_COMMAND**).  
  
## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [CDocument에서에서 문서 클래스 파생](../mfc/deriving-a-document-class-from-cdocument.md)  
  
-   [문서 데이터 변수로 데이터 관리](../mfc/managing-data-with-document-data-variables.md)  
  
-   [파일로 / 파일에서 데이터를 직렬화 하는 작업](../mfc/serializing-data-to-and-from-files.md)  
  
-   [Serialization 메커니즘 건너뛰기](../mfc/bypassing-the-serialization-mechanism.md)  
  
-   [문서에서 명령 처리](../mfc/handling-commands-in-the-document.md)  
  
-   [OnNewDocument 멤버 함수](../mfc/reference/cdocument-class.md#onnewdocument)  
  
-   [DeleteContents 멤버 함수](../mfc/reference/cdocument-class.md#deletecontents)  
  
## <a name="see-also"></a>참고 항목  
 [문서/뷰 아키텍처](../mfc/document-view-architecture.md)

