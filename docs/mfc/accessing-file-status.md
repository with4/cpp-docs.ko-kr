---
title: 파일 상태 액세스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d424502e991ea355a6e31bba8fedccb6d5ad2fcf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-file-status"></a>파일 상태 액세스
`CFile`은 파일 존재 여부, 생성/수정 날짜 및 시간, 논리적 크기와 경로 등을 비롯한 파일 상태도 가져올 수 있습니다.  
  
### <a name="to-get-file-status"></a>파일 상태를 가져오려면  
  
1.  사용 하 여는 [CFile](../mfc/reference/cfile-class.md) 가져오고 파일에 대 한 정보를 설정 하는 클래스입니다. 유용한 응용 프로그램 하나를 사용 하는 것은 `CFile` 정적 멤버 함수 **GetStatus** 파일이 있는지 확인 하려면. **GetStatus** 지정 된 파일이 존재 하지 않는 경우 0을 반환 합니다.  
  
 따라서 결과를 사용할 수 있습니다 **GetStatus** 사용 여부를 결정 하는 **cfile:: Modecreate** 다음 예제에서와 같이 파일을 열 때 플래그:  
  
 [!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]  
  
 관련된 정보를 참조 하십시오. [Serialization](../mfc/serialization-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [파일](../mfc/files-in-mfc.md)

