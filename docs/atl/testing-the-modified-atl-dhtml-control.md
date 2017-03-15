---
title: "Testing the Modified ATL DHTML Control | Microsoft Docs"
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
  - "DHTML controls, 테스트"
  - "HTML 컨트롤, 테스트"
  - "testing controls"
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Testing the Modified ATL DHTML Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이제 작동 방식을 보려면 새로운 컨트롤을 봅니다.  
  
#### 작성 및 수정 된 컨트롤을 테스트 하려면  
  
1.  프로젝트를 다시 빌드한 다음 테스트 컨테이너에서 엽니다.  참조  [속성 및 이벤트 테스트 컨테이너 테스트](../mfc/testing-properties-and-events-with-test-container.md) 테스트 컨테이너에 액세스 하는 방법에 대 한 정보.  
  
     추가한 단추를 모두 표시할 수 있도록 컨트롤 크기를 조정 합니다.  
  
2.  HTML을 변경 하 여 삽입 하는 두 개의 단추를 검사 합니다.  각 단추에서 식별 된 라벨이  [ATL DHTML 컨트롤 수정](../atl/modifying-the-atl-dhtml-control.md):  **새로** 및  **HelloHTML**.  
  
3.  작동 방식을 보려면 두 새 단추를 테스트 합니다.  
  
 이제 UI의 일부가 아닌 메서드를 테스트 합니다.  
  
1.  테두리를 활성화 하도록 컨트롤을 강조 표시 합니다.  
  
2.  에  **컨트롤** 메뉴를 클릭  **메서드 호출**.  
  
 메서드 목록 표시  **메서드 이름** 컨테이너에서 호출할 수 있는 메서드입니다: `MethodInvoked` 및 `GoToURL`.  다른 모든 메서드는 UI에 의해 제어 됩니다.  
  
1.  메서드를 호출 하 고 클릭 선택 `Invoke` 메서드의 메시지 상자를 표시 하거나 www.microsoft.com으로 이동 합니다.  
  
2.  에  **메서드 호출** 대화 상자 클릭  **닫기**.  
  
 다양 한 요소와 ATL DHTML 컨트롤을 구성 하는 파일에 대 한 자세한 내용을 보려면  [DHTML 컨트롤 프로젝트의 요소를 나타내는](../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
## 참고 항목  
 [DHTML 컨트롤에 대한 지원](../atl/atl-support-for-dhtml-controls.md)