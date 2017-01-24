---
title: "CCreateContext Structure | Microsoft Docs"
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
  - "CCreateContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCreateContext structure"
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCreateContext Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프레임 워크를 사용 하는 `CCreateContext` 프레임 창 및 문서와 연결 된 뷰를 만들 때 구성 합니다.  
  
## 구문  
  
```  
struct CCreateContext  
```  
  
## 설명  
 `CCreateContext`구조 이며는 기본 클래스가 없습니다.  
  
 창을 만들 때 값이이 구조에서 문서의 구성 요소는 해당 데이터 보기에 연결 하는 데 사용 되는 정보를 제공 합니다.  사용할 필요가 `CCreateContext` 부분 생성 프로세스를 재정의 하는 경우.  
  
 A `CCreateContext` 구조 문서, 프레임 창, 보기 및 문서 서식 파일에 대 한 포인터를 포함 합니다.  에 대 한 포인터도 포함 되어 있는 `CRuntimeClass` 만들려면 보기의 종류를 식별 합니다.  런타임 클래스 정보 및 현재 문서 포인터가 동적으로 새 뷰를 만드는 데 사용 됩니다.  방법 및 시기는 다음 표에 나와 각 `CCreateContext` 멤버를 사용할 수 있습니다.  
  
|멤버|형식|에 대 한 것|  
|--------|--------|-------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`만들려면 새 보기입니다.|  
|`m_pCurrentDoc`|`CDocument*`|새 뷰를 연관 시킬 기존 문서입니다.|  
|`m_pNewDocTemplate`|`CDocTemplate*`|새 MDI 프레임 창 만들기와 관련 된 문서 템플릿.|  
|`m_pLastView`|`CView*`|원래 보기에서 추가 보기, 분할자 창 보기 만들기 또는 보기 문서 만들기와 같이 모델링 됩니다.|  
|`m_pCurrentFrame`|`CFrameWnd*`|프레임 창에는 추가 프레임 창, 문서에서 두 번째 프레임 창 만들기와 같이 모델링 됩니다.|  
  
 문서 템플릿 문서 및 관련된 구성 요소를 만들 때 저장 된 정보 확인은 `CCreateContext` 구조.  예를 들어, 존재 하지 않는 문서에 대 한 보기를 만들 수 없습니다.  
  
> [!NOTE]
>  모든 포인터를 `CCreateContext` 며 수 `NULL` 지정 되지 않음 이나 알 수 없는 경우.  
  
 `CCreateContext`아래 나열 된 멤버 함수에 의해 사용 되는 "참고 하십시오." 재정의 하는 경우 특정 정보에 대 한 설명은 이러한 함수를 참조 하십시오.  
  
 다음은 몇 가지 일반적인 지침입니다.  
  
-   In 창 작성에 대 한 인수로 전달 될 때 `CWnd::Create`, `CFrameWnd::Create`, 및 `CFrameWnd::LoadFrame`, 어떤 새 창으로 연결 되어야 만들기 컨텍스트를 지정 합니다.  대부분의 windows에 대 한 전체 구조 며 a `NULL` 포인터를 전달할 수 있습니다.  
  
-   재정의 가능한 멤버 함수에 대해 같은 `CFrameWnd::OnCreateClient`, `CCreateContext` 인수는 선택 사항입니다.  
  
-   관련된 멤버 함수에 대 한 뷰 만들기를 하면 보기를 만들 충분 한 정보를 제공 해야 합니다.  예를 들어,에 대 한 첫 번째 보기 분할 창에서 현재 문서 및 뷰 클래스 정보를 제공 해야 합니다.  
  
 일반적으로 기본 프레임 워크를 사용 하는 경우를 무시할 수 있습니다 `CCreateContext`.  고급 수정, Mfc 라이브러리 소스 코드 또는 같은, VIEWEX 샘플 프로그램을 시도 하는 경우 안내 합니다.  필요한 매개 변수가 않으면 framework 어설션 사용 하지 않았습니다 확인할 수 있습니다.  
  
 에 대 한 자세한 내용은 `CCreateContext`, MFC 샘플을 참조 하십시오.  [VIEWEX](../../top/visual-cpp-samples.md).  
  
## 요구 사항  
 **헤더:** afxext.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../Topic/CFrameWnd::Create.md)   
 [CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md)   
 [CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md)   
 [CSplitterWnd::Create](../Topic/CSplitterWnd::Create.md)   
 [CSplitterWnd::CreateView](../Topic/CSplitterWnd::CreateView.md)   
 [CWnd::Create](../Topic/CWnd::Create.md)