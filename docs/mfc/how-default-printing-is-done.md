---
title: "기본 인쇄가 수행되는 방법 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "기본 인쇄"
  - "기본, 인쇄"
  - "인쇄[MFC], default"
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 기본 인쇄가 수행되는 방법
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 MFC framework의 관점에서 Windows의 기본 인쇄 프로세스를 설명합니다.  
  
 MFC 응용 프로그램에서, 뷰 클래스는 모든 그리기 코드를 포함하는 `OnDraw`라고 명명된 멤버 함수를 가집니다.  `OnDraw`는 포인터를 [CDC](../mfc/reference/cdc-class.md)에 매개 변수로서 받습니다.  `CDC` 개체는 `OnDraw`에 의해 생성된 이미지를 받는 장치 컨텍스트를 나타냅니다.  문서를 표시하는 윈도우가 [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) 메세지를 받았을 때, framework는 `OnDraw`을 호출하고 그것을 화면\([CPaintDC](../mfc/reference/cpaintdc-class.md) 개체\)을 위해 장치 컨텍스트에 전달합니다.  따라서, `OnDraw`의 출력은 화면으로 이동합니다.  
  
 Windows 프로그래밍에서, 프린터로 출력을 보내는 것은 화면으로 출력을 보내는 것과 매우 비슷합니다.  Windows 그래픽 장치 인터페이스\(GDI\)가 하드웨어 독립적이기 때문입니다.  화면 표시나 간단히 적절한 디바이스 컨텍스트를 사용한 인쇄를 위해 같은 GDI 함수를 사용할 수 있습니다.  `OnDraw`를 받는 `CDC` 개체가 프린터를 나타내면, `OnDraw`의 출력은 프린터로 이동합니다.  
  
 이것은 MFC 응용 프로그램이 사용자 부분에서 별도 작업 없이 간단한 인쇄를 수행할 수 있는 방법을 설명합니다.  framework는 인쇄 대화 상자 표시와 프린터를 위한 디바이스 컨텍스트 생성을 담당합니다.  사용자가 파일 메뉴에서 인쇄 명령을 선택하면, 보기는 이 장치 컨텍스트를 프린터에서 문서를 그리는 `OnDraw`에 전달합니다.  
  
 그러나, 인쇄 및 화면 표시 사이에는 몇 가지 큰 차이가 있습니다.  프린트할 때, 사용자는 문서를 별개의 페이지로 분할해야 하고 어떤 부분이든 창에서 보이는 부분 대신 그들을 하나로 표시해야 합니다.  그 결과, 사용자는 용지 크기\(그것이 레터 크기든, 법정 규격이든, 봉투이든\)에 유의해야 합니다.  가로 또는 세로 모드처럼 다른 방향으로 인쇄할 수도 있습니다.  MFC 라이브러리는 사용자 응용 프로그램이 이러한 문제를 처리할 방법을 예측할 수 없으므로, 사용자를 위해 이러한 기능을 추가하기 위한 프로토콜을 제공합니다.  
  
 프로토콜은 [Multipage Documents](../mfc/multipage-documents.md)에 설명되어 있습니다..  
  
## 참고 항목  
 [인쇄](../mfc/printing.md)