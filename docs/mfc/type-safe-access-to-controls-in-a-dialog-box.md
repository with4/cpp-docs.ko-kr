---
title: "대화 상자의 컨트롤에 대한 형식이 안전한 액세스 | Microsoft Docs"
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
  - "공용 컨트롤[C++], 대화 상자"
  - "컨트롤[MFC], 대화 상자에서 액세스"
  - "대화 상자[C++], 컨트롤에 대한 형식이 안전한 액세스"
  - "MFC 대화 상자, 컨트롤에 대한 형식이 안전한 액세스"
  - "대화 상자 컨트롤에 대한 안전한 액세스"
  - "대화 상자 컨트롤에 대한 형식이 안전한 액세스"
  - "Windows 공용 컨트롤[C++], 대화 상자"
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 대화 상자의 컨트롤에 대한 형식이 안전한 액세스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대화 상자의 컨트롤에서 `CListBox` 및 `CEdit` 같은 MFC 컨트롤 클래스의 인터페이스를 사용할 수 있습니다.  컨트롤 개체를 만들어 대화 상자 컨트롤에 연결할 수 있습니다.  그런 다음 컨트롤에서 작동하는 멤버 함수를 호출하여 해당 클래스 인터페이스를 통해 컨트롤에 액세스할 수 있습니다.  컨트롤에 대한 형식 안전 액세스를 제공하기 위해 여기서 설명한 방법이 설계되었습니다.  특히 입력란 및 목록 상자 같은 컨트롤에 유용합니다.  
  
 `CDialog`에서 파생된 클래스에서 대화 상자의 컨트롤과 C\+\+ 컨트롤 멤버 변수 간에 연결하기 위한 두 가지 방법은 다음과 같습니다.  
  
-   [코드 마법사를 사용하지 않는 경우](../mfc/type-safe-access-to-controls-without-code-wizards.md)  
  
-   [코드 마법사를 사용하는 경우](../mfc/type-safe-access-to-controls-with-code-wizards.md)  
  
## 참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)