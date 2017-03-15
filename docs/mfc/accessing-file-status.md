---
title: "파일 상태 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "예제[MFC], 파일 상태"
  - "파일 상태[C++]"
  - "파일[C++], 액세스"
  - "파일[C++], 상태 정보"
  - "파일 상태"
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 파일 상태 액세스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CFile` 는 파일의 존재여부를 포함하여 생성과 수정날짜 및 시간, 논리정 크기와 경로등의 파일 상태를 얻을 수 있도록 지원해 줍니다.  
  
### 파일 상태를 가져오기.  
  
1.  파일에 관한 정보를 설정하고 가져오기 위해 [CFile](../mfc/reference/cfile-class.md) 클래스를 사용합니다.  유용한 응용 프로그램 하나는 만일 파일이 존재한다면 파일이 있는지 확인하기 위해 `CFile` 정적 멤버 함수인 **GetStatus** 을 사용하는 것입니다.  만일 지정된 파일이 존재하지 않는 다면 **GetStatus** 는 0을 반환합니다.  
  
 따라서, 다음 예제에서 보이는 것 처럼, 파일을 열때, **CFile::modeCreate** 플래그의 사용 여부를 결정하기 위해 **GetStatus** 의 결과를 사용할 수 있습니다.  
  
 [!code-cpp[NVC_MFCFiles#3](../mfc/codesnippet/CPP/accessing-file-status_1.cpp)]  
  
 이에 대한 관련 내용은, [Serialization](../mfc/serialization-in-mfc.md) 를 참고하세요.  
  
## 참고 항목  
 [파일](../mfc/files-in-mfc.md)