---
title: 파일 닫기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97bd910ae4cb514cda07dd319f37a05a32712909
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="closing-files"></a>파일 닫기
평소와 같이 I/O 작업에서 파일을 완료 한 후 닫아야 합니다.  
  
#### <a name="to-close-a-file"></a>파일을 닫으려면  
  
1.  사용 하 여 **닫기** 멤버 함수입니다. 이 함수는 파일 시스템 파일을 닫고 필요에 따라 버퍼를 플러시합니다.  
  
 할당 한 경우는 [CFile](../mfc/reference/cfile-class.md) 프레임에 개체 (예제에서 같이 [파일 열기](../mfc/opening-files.md)), 개체는 자동으로 닫히고 다음 범위를 벗어나면 소멸 합니다. 삭제할 참고는 `CFile` 개체는 파일 시스템의 물리적 파일을 삭제 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [파일](../mfc/files-in-mfc.md)

