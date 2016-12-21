---
title: "끌어서 놓기: 사용자 지정 | Microsoft Docs"
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
  - "끌어서 놓기, DoDragDrop 호출"
  - "끌어서 놓기, COleDataSource 개체"
  - "끌어서 놓기, 동작 사용자 지정"
  - "끌어서 놓기, 비OLE 응용 프로그램에 구현"
  - "OLE 끌어서 놓기, 동작 사용자 지정"
ms.assetid: 03369d3e-46bf-4140-b58c-d0c9657cf38a
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 끌어서 놓기: 사용자 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

끌어서 놓기 기능을 기본적으로 대부분의 응용 프로그램에 충분 합니다.  그러나 일부 응용 프로그램에서는이 표준 동작을 변경 하는 것입니다.  이 문서는 이러한 기본값을 변경 하는 데 필요한 단계를 설명 합니다.  또한 끌어 놓기 소스로 복합 문서를 지원 하지 않는 응용 프로그램을 설정 하려면이 방법을 사용할 수 있습니다.  
  
 표준 OLE 끌어서 놓기 동작을 사용자 지정 하 고 또는 비 OLE 응용 프로그램을 작성 해야 한  `COleDataSource`  데이터를 포함 하는 개체입니다.  끌어서 놓기 작업을 시작할 때 코드를 호출 해야 하면  `DoDragDrop`  함수에서 끌어서 놓기 작업을 지 원하는 기타 클래스 대신이 개체입니다.  
  
 만들 수 있습니다 한  `COleDropSource`  개체 드롭다운 컨트롤을 변경 하려면 동작의 형식에 따라 기능 중 일부를 재정의할 수 있습니다.  이 소스 개체에 전달 됩니다  `COleDataSource::DoDragDrop`  이러한 함수의 기본 동작을 변경할 수 있습니다.  이러한 다양 한 옵션 많은 응용 프로그램에서 끌어서 놓기 작업을 지 원하는 방법의 유연성을 허용 합니다.  데이터 원본에 대 한 자세한 내용은 문서를 참조 하십시오. [데이터 개체 및 데이터 소스 \(OLE\)](../mfc/data-objects-and-data-sources-ole.md).  
  
 끌어서 놓기 작업을 사용자 지정 하려면 다음과 같은 함수를 재정의할 수 있습니다.  
  
|재정의|사용자 지정:|  
|---------|-------------|  
|`OnBeginDrag`|드래그를 호출한 후 시작 되는 방법을  `DoDragDrop`  알 수 있습니다.|  
|`GiveFeedback`|예: 커서 모양, 다양 한 놓기 결과 대 한 시각적 피드백|  
|`QueryContinueDrag`|끌어서 놓기 작업을 종료 합니다.  이 함수를 사용 하면 끌기 작업 도중 한정자 키 상태를 확인할 수 있습니다.|  
  
## 참고 항목  
 [끌어서 놓기\(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDropSource Class](../mfc/reference/coledropsource-class.md)   
 [COleDataSource Class](../mfc/reference/coledatasource-class.md)