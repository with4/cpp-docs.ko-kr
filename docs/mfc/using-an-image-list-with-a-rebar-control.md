---
title: "이미지 목록과 Rebar 컨트롤 함께 사용 | Microsoft Docs"
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
  - "이미지 목록[C++], rebar 컨트롤"
  - "rebar 컨트롤, 이미지 목록"
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 이미지 목록과 Rebar 컨트롤 함께 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각 rebar 밴드는 연결된 이미지 목록으로부터 이미지와, 관련된 다른 것들을 포함할 수 있습니다.  다음 절차는 rebar 밴드에서 이미지를 표시하는데 필요한 단계를 자세히 설명합니다.  
  
### rebar 밴드에서 이미지를 표시하려면  
  
1.  [SetlmageList](../Topic/CReBarCtrl::SetImageList.md)로 호출을 만드는 것에 의해 revat 컨트롤 개체로 이미지 목록을 연결하고, 기존의 이미지 목록으로 포인터를 전달합니다.  
  
2.  rebar 밴드로 이미지를 할당하기 위해 **REBARBANDINFO** 구조체를 수정합니다:  
  
    -   필요에 따라 추가적인 플래그들을 포함하기 위해 비트연산자 OR을 사용하여 **RBBIM\_IMAGE** 로 **fMask** 멤버를 설정합니다.  
  
    -   표시될 이미지의 이미지 목록 인덱스로 `iImage` 멤버를 설정합니다.  
  
3.  필수적인 정보를 사용하여 자식 창을 포함하는 핸들과 텍스트, 크기와 같은 나머지 모든 데이터 멤버들을 초기화합니다.  
  
4.  [CReBarCtrl::InsertBand](../Topic/CReBarCtrl::InsertBand.md) 로 호출을 사용하여 새 밴드\(이미지와 함께\)를 삽입하고, **REBARBANDINFO** 구조체를 전달합니다.  
  
 다음 예제는 rebar 컨트롤 개체\(`m_wndReBar`\)로 연결된 두 이미지들을 사용하여 기존의 이미지 목록을 가정합니다.  첫번째 이미지를 포함하는 \(`rbi` 에 의해 정의된\) 새 rebar 밴드는 `InsertBand` 로 호출을 사용하여 추가됩니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/CPP/using-an-image-list-with-a-rebar-control_1.cpp)]  
  
## 참고 항목  
 [CReBarCtrl 사용](../mfc/using-crebarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)