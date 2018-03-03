---
title: "파일 I/o 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.file
dev_langs:
- C++
helpviewer_keywords:
- disk file classes [MFC]
- stdio classes [MFC]
- OLE streams [MFC]
- I/O [MFC], MFC classes
- translated stream classes [MFC]
- file I/O classes [MFC]
- I/O [MFC], classes
- sockets classes [MFC]
- stream classes [MFC]
- memory file classes [MFC]
ms.assetid: 92821c3f-d9e1-47f6-98c9-3b632d86e811
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 454e64d67321282030126d2aab023e9f587c1cca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="file-io-classes"></a>파일 I/O 클래스
이러한 클래스는 기존의 디스크 파일, 메모리에 파일, 활성 스트림, 및 Windows 소켓에 대 한 인터페이스를 제공합니다. 파생 된 모든 클래스 `CFile` 와 함께 사용할 수는 `CArchive` 개체를 직렬화를 수행 합니다.  
  
 특히 다음 클래스를 사용 하 여 `CArchive` 및 `CFile`입/출력 처리를 작성 하는 경우, 합니다. 일반적으로 이러한 클래스에서 파생 될 필요가 없습니다. 응용 프로그램 프레임 워크의 기본 구현을 사용 하는 경우는 **열려** 및 **저장** 에 있는 명령을 **파일** 메뉴 파일 I/O를 처리 합니다 ( 클래스를사용하여`CArchive`) 문서의 재정의 `Serialize` 문서에서 해당 콘텐츠를 직렬화 하는 방법을 대 한 자세한 내용을 제공 하는 함수입니다. 파일 클래스 및 serialization에 대 한 자세한 내용은 문서 참조 [MFC의 파일](../mfc/files-in-mfc.md) 및 문서 [Serialization](../mfc/serialization-in-mfc.md)합니다.  
  
 [CFile](../mfc/reference/cfile-class.md)  
 이진 디스크 파일에 파일 인터페이스를 제공합니다.  
  
 [CStdioFile](../mfc/reference/cstdiofile-class.md)  
 제공 된 `CFile` 텍스트 모드에서 일반적으로 버퍼링 된 스트림 디스크 파일에 대 한 인터페이스입니다.  
  
 [CMemFile](../mfc/reference/cmemfile-class.md)  
 제공 된 `CFile` 메모리 파일에 대 한 인터페이스입니다.  
  
 [CSharedFile](../mfc/reference/csharedfile-class.md)  
 제공 된 `CFile` 공유 메모리 파일에 대 한 인터페이스입니다.  
  
 [COleStreamFile](../mfc/reference/colestreamfile-class.md)  
 COM을 사용 하 여 `IStream` 인터페이스를 `CFile` 복합 파일에 대 한 액세스.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 제공 된 `CFile` Windows 소켓에 대 한 인터페이스입니다.  
  
## <a name="related-classes"></a>관련된 클래스  
 [CArchive](../mfc/reference/carchive-class.md)  
 와 협력 하 여 한 `CFile` serialization 통해 개체에 대 한 영구 저장소를 구현 하는 개체 (참조 [cobject:: Serialize](../mfc/reference/cobject-class.md#serialize)).  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 아카이브 예외입니다.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 파일 관련 예외입니다.  
  
 [CFileDialog](../mfc/reference/cfiledialog-class.md)  
 열기 또는 저장 된 파일에 대 한 표준 대화 상자를 제공 합니다.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 가장 최근에 사용한 (MRU) 파일 목록 유지 관리 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

