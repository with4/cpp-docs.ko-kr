---
title: "끌어서 놓기: 놓기 대상 구현 | Microsoft Docs"
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
  - "끌어서 놓기, 놓기 대상"
  - "OLE 끌어서 놓기, 놓기 대상"
  - "OLE 끌어서 놓기, 놓기 대상 구현"
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 끌어서 놓기: 놓기 대상 구현
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 드롭 대상 응용 프로그램을 만드는 방법을 설명 합니다.  드롭 대상 구현은 드롭 소스 구현 보다 약간 더 많은 작업이 필요 하지만 여전히 상대적으로 간단 합니다.  이러한 기술은 비 OLE 응용 프로그램에도 적용 됩니다.  
  
#### 드롭 대상을 구현하려면  
  
1.  드롭 대상이 될 응용 프로그램의 각 뷰에 멤버 변수를 추가 합니다.  멤버 변수는 `COleDropTarget` 형식이거나 파생 된 클래스여야 합니다.  
  
2.  `WM_CREATE` 메시지를 처리하는 뷰 클래스의 함수에서 \(일반적으로 `OnCreate`\) 새 멤버 변수의 `Register` 멤버 함수를 호출합니다.  `Revoke`는 보기가 소멸될 때 자동으로 호출됩니다.  
  
3.  다음 함수를 재정의 합니다.  응용 프로그램 전체에서 동일 하게 동작을 원하는 경우 뷰 클래스에 이 함수를 재정의 합니다.  격리 된 경우 동작을 수정하거나 비 `CView` 창에서 드롭을 허용하는 경우, `COleDropTarget` 파생 클래스에서 해당 함수를 재정의 하십시오.  
  
    |재정의|허용하려면|  
    |---------|-----------|  
    |`OnDragEnter`|창에서 발생 하는 작업을 삭제 합니다.  커서를 창으로 처음 가져가면 호출됩니다.|  
    |`OnDragLeave`|끌기 작업이 지정된 된 창을 나갈 때 특별한 동작입니다.|  
    |`OnDragOver`|창에서 발생 하는 작업을 삭제 합니다.  창에서 커서를 끌 때 호출 됩니다.|  
    |`OnDrop`|지정된 된 창 안에 놓이는 데이터를 처리 합니다.|  
    |`OnScrollBy`|스크롤이 필요할 때 대상 창에 대한 특별 작업입니다.|  
  
 함수가 어떻게 함께 작동하는지에 대한 예제의 [OCLIENT](../top/visual-cpp-samples.md) MFC OLE 샘플의 일부로 MAINVIEW.CPP 파일을 참조하십시오.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [끌어 놓기 소스 구현](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [OLE 데이터 개체 및 데이터 소스를 생성하거나 소멸시키기](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [데이터 개체 및 데이터 소스 조작](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## 참고 항목  
 [끌어서 놓기\(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDropTarget Class](../mfc/reference/coledroptarget-class.md)