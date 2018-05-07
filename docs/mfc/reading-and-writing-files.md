---
title: 파일 읽기 및 쓰기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CFile class [MFC], objects
- examples [MFC], reading files
- files [MFC], writing to
- examples [MFC], writing to files
- files [MFC], reading
- MFC, file operations
- CFile class [MFC], reading and writing CFile objects
- reading files
- writing to files [MFC]
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 102f5f5de591f8a4475232ad8f0f5383c276e5d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="reading-and-writing-files"></a>파일 읽기 및 쓰기
C 런타임 라이브러리 파일 처리 함수를 사용한 경우 읽기 및 쓰기 작업이 MFC 쉬울 것입니다. 이 문서에서는 직접 읽기 및 쓰기에 직접 설명는 `CFile` 개체입니다. 있습니다 수 또한 않습니다 버퍼링 파일 I/O에는 [CArchive](../mfc/reference/carchive-class.md) 클래스입니다.  
  
#### <a name="to-read-from-and-write-to-the-file"></a>읽고 파일에 쓸  
  
1.  사용 하 여는 **읽기** 및 **쓰기** 읽고 파일에 데이터를 기록 하는 멤버 함수입니다.  
  
     -또는-  
  
2.  `Seek` 멤버 함수는 파일 내에서 특정 오프셋으로 이동 가능 합니다.  
  
 **읽기** 읽을 바이트 수와 버퍼에 대 한 포인터를 사용 하 고 실제 읽은 바이트 수를 반환 합니다. 필요한 바이트 수가 로드할 수 때문에 파일 끝 (EOF)에 도달 하면, 실제 읽은 바이트 수가 반환 됩니다. 읽기 오류가 발생 하는 경우 예외가 throw 됩니다. **쓰기** 비슷합니다 **읽기**, 하지만 쓴 바이트 수가 반환 되지 않습니다. 를 지정 하는 모든 바이트를 쓰지 않습니다. 포함 하 여 쓰기 오류가 발생 하면 예외가 throw 됩니다. 유효한 있으면 `CFile` 개체에서 읽거나 다음 예제와 같이에 쓸 수 있습니다.  
  
 [!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]  
  
> [!NOTE]
>  내에서 입/출력 작업을 정상적으로 수행 해야는 **시도**/**catch** 예외 블록을 처리 합니다. 자세한 내용은 참조 [예외 처리 (MFC)](../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [파일](../mfc/files-in-mfc.md)

