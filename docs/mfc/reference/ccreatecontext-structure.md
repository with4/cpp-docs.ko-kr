---
title: "CCreateContext 구조 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCreateContext
dev_langs:
- C++
helpviewer_keywords:
- CCreateContext structure
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 231f2e44e085d27a2b2cbf289adf7b0521471b0e
ms.lasthandoff: 02/24/2017

---
# <a name="ccreatecontext-structure"></a>CCreateContext 구조
프레임 워크를 사용 하는 `CCreateContext` 프레임 창 및 문서와 연결 된 뷰를 만들 때 구성 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CCreateContext  
```  
  
## <a name="remarks"></a>주의  
 `CCreateContext`구조와 기본 클래스는 없습니다.  
  
 창을 만들 때이 구조체의 값 데이터의 보기에는 문서의 구성 요소를 연결 하는 데 사용 되는 정보를 제공 합니다. 사용 해야 `CCreateContext` 생성 프로세스의 부분을 재정의 하는 경우.  
  
 A `CCreateContext` 구조 문서, 프레임 창, 보기 및 문서 서식 파일에 대 한 포인터를 포함 합니다. 에 대 한 포인터도 포함 한 `CRuntimeClass` 만들려는 보기의 유형을 식별 하는 합니다. 런타임 클래스 정보 및 현재 문서 포인터는 새 뷰를 동적으로 작성 하는 데 사용 됩니다. 다음 표에서 시기와 방법을 제안 각 `CCreateContext` 멤버를 사용할 수 있습니다.  
  
|멤버|형식|에 대 한|  
|------------|----------|--------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`새 보기를 만듭니다.|  
|`m_pCurrentDoc`|`CDocument*`|새 보기와 연결할 기존 문서입니다.|  
|`m_pNewDocTemplate`|`CDocTemplate*`|문서 서식 파일을 새 MDI 프레임 창 만드는 연관 됩니다.|  
|`m_pLastView`|`CView*`|원래 보기 있는 추가 보기 모델링 되며, 분할 창 보기 생성 또는 문서에서 두 번째 뷰 생성 합니다.|  
|`m_pCurrentFrame`|`CFrameWnd*`|프레임 창에 추가 프레임 창 모델링 되며, 문서에서 두 번째 프레임 창 만드는와 같이 합니다.|  
  
 에 저장 된 정보는 문서 템플릿을 문서 및 관련된 구성 요소를 만들 때 유효성을 검사는 `CCreateContext` 구조입니다. 예를 들어 존재 하지 않는 문서에 대 한 보기를 만들 수 없습니다.  
  
> [!NOTE]
>  에 대 한 포인터의 모든 `CCreateContext` 는 선택 사항이 며 수 `NULL` 지정 되지 않은 또는 알 수 없는 경우.  
  
 `CCreateContext`아래에 나열 된 멤버 함수에서 사용 하는 "를 참조 하십시오." 재정의 하려는 경우 특정 정보에 대 한 이러한 함수에 대 한 설명을 참조 하십시오.  
  
 다음은 몇 가지 일반적인 지침입니다.  
  
-   와 같이 창 만들기에 대 한 인수로 전달 될 때 `CWnd::Create`, `CFrameWnd::Create`, 및 `CFrameWnd::LoadFrame`, 만들기 컨텍스트 무엇 새 창에 연결할지를 지정 합니다. 대부분의 windows에 대 한 전체 구조는 선택 사항 및 `NULL` 포인터를 전달할 수 있습니다.  
  
-   재정의 가능한 멤버 함수에 대 한 예: `CFrameWnd::OnCreateClient`, `CCreateContext` 인수는 선택 사항입니다.  
  
-   관련 된 멤버 함수에 대 한 뷰를 만드는 제공 해야 뷰를 만드는 데 충분 한 정보. 예를 들어 분할 창에서 첫 번째 뷰를 제공 해야 클래스 정보 보기 및 현재 문서입니다.  
  
 일반적으로 프레임 워크 기본값을 사용 하는 경우 무시 해도 `CCreateContext`합니다. 고급 수정, Microsoft Foundation Class 라이브러리 소스 코드 또는 VIEWEX, 같은 샘플 프로그램을 사용 하려는 경우를 안내 합니다. 필수 매개 변수를 잊어버리면 프레임 워크 어설션을 알려 줍니다 잊음 있습니다.  
  
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


