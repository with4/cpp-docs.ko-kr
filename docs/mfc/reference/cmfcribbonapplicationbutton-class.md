---
title: "CMFCRibbonApplicationButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonApplicationButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonApplicationButton class"
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonApplicationButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implements는 특수 단추 응용 프로그램 창의 왼쪽 위 모서리에 있는.  클릭할 단추 포함 일반적인 메뉴 열리는  **파일** 명령을 다음과 같이  **열려**,  **저장**, 및  **종료**.  
  
## 구문  
  
```  
class CMFCRibbonApplicationButton : public CMFCRibbonButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](../Topic/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton.md)|생성 및 초기화는 `CMFCRibbonApplicationButton` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCRibbonApplicationButton::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|`CMFCRibbonApplicationButton::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCRibbonApplicationButton::SetImage](../Topic/CMFCRibbonApplicationButton::SetImage.md)|리본 응용 프로그램 단추에 이미지를 할당합니다.|  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CMFCRibbonApplicationButton` 클래스입니다.  이 예제에서는 응용 프로그램 단추에 이미지를 할당 하는 방법 및 해당 도구 설명을 설정 하는 방법을 보여 줍니다.  이 코드 조각에 속하지는  [그릴 클라이언트 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/CPP/cmfcribbonapplicationbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/CPP/cmfcribbonapplicationbutton-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)  
  
## 요구 사항  
 **헤더:** afxRibbonBar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)