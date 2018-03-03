---
title: "CCreateContext 구조 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCreateContext
dev_langs:
- C++
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 929ed0971f9b69bf8e98ae247957110e78ac33ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccreatecontext-structure"></a>CCreateContext 구조
프레임 워크를 사용 하 여는 `CCreateContext` 프레임 창 및 문서와 연결 된 뷰를 만들 때 구성 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CCreateContext  
```  
  
## <a name="remarks"></a>설명  
 `CCreateContext`구조체가 고 기본 클래스는 없습니다.  
  
 창을 만들 때이 구조에서는 값 데이터의 보기를 문서의 구성 요소를 연결 하는 데 사용 되는 정보를 제공 합니다. 사용 해야 `CCreateContext` 생성 프로세스의 일부를 재정의 하는 경우.  
  
 A `CCreateContext` 구조는 문서, 프레임 창, 보기 및 문서 서식 파일에 대 한 포인터를 포함 합니다. 에 대 한 포인터도 포함 한 `CRuntimeClass` 만들려는 보기의 유형을 식별 하는 합니다. 런타임 클래스 정보 및 현재 문서 포인터를 동적으로 새 보기를 만들려면 사용 됩니다. 다음 표에서 시기와 방법을 제안 각 `CCreateContext` 멤버를 사용할 수 있습니다.  
  
|멤버|형식|이 대 한|  
|------------|----------|--------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`만들려는 새 뷰의 합니다.|  
|`m_pCurrentDoc`|`CDocument*`|새 보기와 연결할 기존 문서입니다.|  
|`m_pNewDocTemplate`|`CDocTemplate*`|새 MDI 프레임 창 만들기와 관련 된 문서 서식 파일|  
|`m_pLastView`|`CView*`|에 추가 뷰가 모델링 됩니다, 분할 창 보기 생성 또는 문서에 두 번째 뷰 생성에서와 같이 원래 보기입니다.|  
|`m_pCurrentFrame`|`CFrameWnd*`|프레임 창에 추가 프레임 창을 모델링 되며, 문서에 두 번째 프레임 창 만드는와 같이 합니다.|  
  
 에 저장 된 정보는 문서 템플릿을 문서 및 관련된 구성 요소를 만들 때 유효성을 검사는 `CCreateContext` 구조입니다. 예를 들어 존재 하지 않는 문서에 대 한 보기를 만들 수 없습니다.  
  
> [!NOTE]
>  포인터의 모든 `CCreateContext` 선택 사항이 며 수 `NULL` 지정 되지 않은 또는 알 수 없는 경우.  
  
 `CCreateContext`아래 나열 된 멤버 함수에서 사용 하는 "를 참조 하십시오." 재정의 하려는 경우 특정 정보에 대 한 이러한 함수의 설명을 참조 하십시오.  
  
 다음은 몇 가지 일반 지침입니다.  
  
-   와 같이 창 만들기에 대 한 인수로 전달 될 때 `CWnd::Create`, `CFrameWnd::Create`, 및 `CFrameWnd::LoadFrame`, create 컨텍스트 지정 무엇 새 창에 연결 해야 합니다. 대부분의 windows에 대 한 전체 구조는 선택 사항 및 `NULL` 포인터를 전달할 수 있습니다.  
  
-   재정의 가능한 멤버 함수에 대 한 같은 `CFrameWnd::OnCreateClient`, `CCreateContext` 인수는 선택 사항입니다.  
  
-   관련 된 멤버 함수에 대 한 뷰를 만드는 제공 해야 보기를 만드는 데 필요한 충분 한 정보. 예를 들어 분할 창에서 첫 번째 보기에 대 한 클래스 정보 보기 및 현재 문서를 제공 해야 있습니다.  
  
 일반적으로 프레임 워크 기본값을 사용 하는 경우 무시 해도 `CCreateContext`합니다. 더 많은 고급 수정, Microsoft Foundation Class 라이브러리 소스 코드 또는 샘플 프로그램 VIEWEX, 등을 시도 하면를 안내 합니다. 필수 매개 변수를 잊어버리면 프레임 워크 어설션 알려 줍니다 찾기 있습니다.  
  
 대 한 자세한 내용은 `CCreateContext`, MFC 샘플 [VIEWEX](../../visual-cpp-samples.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxext.h  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)   
 [CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)   
 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)   
 [CSplitterWnd::Create](../../mfc/reference/csplitterwnd-class.md#create)   
 [CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)   
 [CWnd::Create](../../mfc/reference/cwnd-class.md#create)

