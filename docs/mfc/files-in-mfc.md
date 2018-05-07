---
title: MFC의 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serialization [MFC], MFC files
- I/O [MFC], MFC classes
- files [MFC], MFC
- files [MFC], serialization
- binary access, binary file operations in MFC
- file I/O classes [MFC]
- I/O [MFC]
- persistence [MFC]
- MFC, file operations
- files [MFC], manipulating
- binary access [MFC]
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30d220c928f2ca3fe0594d03d558d2d6dcfce773
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="files-in-mfc"></a>MFC의 파일
에 MFC Microsoft Foundation Class 라이브러리 (), 클래스 [CFile](../mfc/reference/cfile-class.md) 일반적인 파일 I/O 작업을 처리 합니다. 이 문서 열기 및 파일을 닫고 뿐만 아니라 데이터 읽기 및 쓰기를 해당 파일에 하는 방법을 설명 합니다. 또한 파일 상태 작업에 설명 합니다. 데이터 읽기 및 쓰기 파일에는 대체 방법으로 MFC의 serialization 개체 기반 기능을 사용 하는 방법에 대 한 문서를 참조 [Serialization](../mfc/serialization-in-mfc.md)합니다.  
  
> [!NOTE]
>  MFC를 사용 하는 경우 **CDocument** 개체, 프레임 워크는 serialization 작업의 대부분을 수행 합니다. 특히, 프레임 워크에서 만들고 사용 하 여 `CFile` 개체입니다. 재정의에서 코드를 작성 해야는 `Serialize` 클래스의 멤버 함수 **CDocument**합니다.  
  
 `CFile` 클래스는 일반적인 이진 파일 작업에 대 한 인터페이스를 제공 합니다. `CStdioFile` 및 `CMemFile` 클래스에서 파생 된 `CFile` 및 `CSharedFile` 에서 파생 된 클래스 `CMemFile` 더 특수 한 파일 서비스를 제공 합니다.  
  
 MFC 파일 처리에 대 한 대안에 대 한 자세한 내용은 참조 [파일 처리](../c-runtime-library/file-handling.md) 에 *런타임 라이브러리 참조*합니다.  
  
 에 대 한 정보에 대 한 파생 `CFile` 클래스 참조는 [MFC 계층 구조 차트](../mfc/hierarchy-chart.md)합니다.  
  
## <a name="what-do-you-want-to-do"></a>뭘 하고 싶으세요  
 *CFile 사용*  
  
-   [CFile로 파일을 열으십시오](../mfc/opening-files.md)  
  
-   [읽기 및 쓰기 cfile 파일](../mfc/reading-and-writing-files.md)  
  
-   [Cfile 파일 닫기](../mfc/closing-files.md)  
  
-   [Cfile 파일 상태 액세스](../mfc/accessing-file-status.md)  
  
 *MFC Serialization (개체 지 속성)를 사용 하 여*  
  
-   [Serializable 클래스 만들기](../mfc/serialization-making-a-serializable-class.md)  
  
-   [CArchive 개체를 통해 개체를 직렬화](../mfc/serialization-serializing-an-object.md)  
  
-   [CArchive 개체 만들기](../mfc/two-ways-to-create-a-carchive-object.md)  
  
-   [CArchive를 사용 하 여 <\< 및 >> 연산자](../mfc/using-the-carchive-output-and-input-operators.md)  
  
-   [저장 및 로드 CObjects 및 보관을 통해 CObject 파생 개체](../mfc/storing-and-loading-cobjects-via-an-archive.md)  
  
## <a name="see-also"></a>참고 항목  
 [개념](../mfc/mfc-concepts.md)   
 [일반 MFC 항목](../mfc/general-mfc-topics.md)   
 [CArchive 클래스](../mfc/reference/carchive-class.md)   
 [CObject 클래스](../mfc/reference/cobject-class.md)
