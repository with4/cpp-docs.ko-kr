---
title: "Testing the ATL DHTML Control | Microsoft Docs"
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
  - "DHTML controls"
  - "DHTML controls, 테스트"
  - "HTML 컨트롤, 테스트"
  - "testing controls"
ms.assetid: 0e4b4358-80ce-4505-8b06-ef4f30b1d1f0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Testing the ATL DHTML Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로젝트를 만든 후에 빌드 및 샘플 컨트롤을 테스트 합니다.  이렇게 하려면 솔루션 탐색기 및 클래스 뷰 프로젝트를 검사할 수 있습니다.  프로젝트의 요소에서 자세히 설명 되어  [DHTML 컨트롤 프로젝트의 요소를 나타내는](../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
#### 빌드 및 ATL DHTML 컨트롤을 테스트 하려면  
  
1.  프로젝트를 빌드합니다.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
2.  빌드가 완료 되 면 테스트 컨테이너를 엽니다.  참조  [속성 및 이벤트 테스트 컨테이너 테스트](../mfc/testing-properties-and-events-with-test-container.md) 테스트 컨테이너에 액세스 하는 방법에 대 한 정보.  
  
3.  테스트 컨테이너에서에서  **편집** 메뉴를 클릭  **새 컨트롤 삽입**.  
  
4.  에  **컨트롤 삽입** 대화 상자에서 목록 상자에서 컨트롤을 선택 합니다.  기억 말씀 ATL 컨트롤 마법사에서 약식 이름 이름을 기반으로 합니다.  **확인**을 클릭합니다.  
  
5.  컨트롤을 검사 합니다.  참고 스크롤 막대가 있는 것입니다.  컨트롤의 핸들을 사용 하 여 스크롤 막대를 활성화 하려면 컨트롤 크기를 조정 합니다.  
  
6.  컨트롤의 단추를 테스트 합니다.  해당 버튼이 가리키는 색 배경 색을 변경 합니다.  
  
7.  테스트 컨테이너를 닫습니다.  
  
 그런 다음,  [DHTML 컨트롤 수정](../atl/modifying-the-atl-dhtml-control.md).  
  
## 참고 항목  
 [DHTML 컨트롤에 대한 지원](../atl/atl-support-for-dhtml-controls.md)