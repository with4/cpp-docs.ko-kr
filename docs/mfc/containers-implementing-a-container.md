---
title: '컨테이너: 컨테이너 구현 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [OLE], OLE container
- OLE containers [MFC], implementing
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3693cb7d52a048045f4745b69b45cacc4defc75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342832"
---
# <a name="containers-implementing-a-container"></a>컨테이너: 컨테이너 구현
이 문서는 컨테이너를 구현 하기 위한 절차를 요약 하 고 보다 자세한 컨테이너를 구현 하는 방법에 대 한 설명을 제공 하는 다른 문서를 소개 합니다. 또한 구현 하려면 몇 가지 선택적 OLE 기능 및 이러한 기능을 설명 하는 문서를 나열 합니다.  
  
#### <a name="to-prepare-your-cwinapp-derived-class"></a>CWinApp에서 파생 된 클래스를 준비 하려면  
  
1.  호출 하 여 OLE 라이브러리 초기화 **AfxOleInit** 에 `InitInstance` 멤버 함수입니다.  
  
2.  호출 `CDocTemplate::SetContainerInfo` 에 `InitInstance` 포함된 된 항목은 사용 하는 리소스의 내부 활성화는 메뉴 및 액셀러레이터를 할당 하려면. 이 항목에 대 한 자세한 내용은 참조 하십시오. [활성화](../mfc/activation-cpp.md)합니다.  
  
 이러한 기능은 MFC 응용 프로그램 마법사를 사용 하 여 컨테이너 응용 프로그램을 만들 때 하기 위해 제공 됩니다. 참조 [MFC EXE 프로그램 만들기](../mfc/reference/mfc-application-wizard.md)합니다.  
  
#### <a name="to-prepare-your-view-class"></a>뷰 클래스를 준비 하려면  
  
1.  포인터를 유지 관리 하 여 선택한 항목 한 추적 또는 나열 하 여 선택한 항목에 여러 선택 영역을 지 원하는 경우 포인터의 합니다. 프로그램 `OnDraw` 함수는 모든 OLE 항목도 그립니다 해야 합니다.  
  
2.  재정의 `IsSelected` 전달 된 항목이 현재 선택 되어 있는지 여부를 확인 합니다.  
  
3.  구현 된 **OnInsertObject** 메시지를 표시 하는 처리기는 **개체 삽입** 대화 상자.  
  
4.  구현 된 `OnSetFocus` 메시지 처리기를 현재 위치 활성화 ole 보기에서 포커스를 항목을 포함 합니다.  
  
5.  구현 된 `OnSize` OLE를 알리기 위해 메시지 처리기를 뷰의 크기의 변경을 반영 하기 위해 해당 영역을 변경 해야 할 항목 포함 합니다.  
  
 이러한 기능을 구현에서 응용 프로그램 마다 크게 다릅니다 때문에 응용 프로그램 마법사만 기본 구현을 제공 합니다. 응용 프로그램을 제대로 작동 하도록 하기 위해 이러한 함수를 사용자 지정할 수 있을 것입니다. 이 예제를 보려면는 [컨테이너](../visual-cpp-samples.md) 샘플.  
  
#### <a name="to-handle-embedded-and-linked-items"></a>포함 및 연결 된 항목을 처리 하려면  
  
1.  클래스를 파생 [COleClientItem](../mfc/reference/coleclientitem-class.md)합니다. 이 클래스의 개체에 포함 되거나 OLE 문서에 연결 된 항목을 나타냅니다.  
  
2.  재정의 **OnChange**, `OnChangeItemPosition`, 및 `OnGetItemPosition`합니다. 이러한 함수는 크기 조정, 위치 지정 및 수정 포함 및 연결 된 항목을 처리 합니다.  
  
 응용 프로그램 마법사는 클래스를 파생 하지만 재정의 해야 합니다 **OnChange** 이전 절차의 2 단계에서와 다른 함수를 나열 합니다. 기본 구현을 이러한 함수에서 하나의 응용 프로그램 마다 다르게 구현 되므로 대부분의 응용 프로그램에 대 한 사용자 지정 해야 합니다. 이 예에서는 MFC 샘플을 참조 [DRAWCLI](../visual-cpp-samples.md) 및 [컨테이너](../visual-cpp-samples.md)합니다.  
  
 OLE를 지원 하기 위해 컨테이너 응용 프로그램의 메뉴 구조에 항목의 수를 추가 해야 합니다. 자세한 내용은 다음을 참조 하십시오. [메뉴 및 리소스: 컨테이너 추가](../mfc/menus-and-resources-container-additions.md)합니다.  
  
 컨테이너 응용 프로그램에서 다음 기능 중 일부를 지원 하려면:  
  
-   포함된 된 항목을 편집 하는 경우에 내부 활성화 합니다.  
  
     자세한 내용은 참조 [활성화](../mfc/activation-cpp.md)합니다.  
  
-   OLE 항목 만들기 끌어서 서버 응용 프로그램에서 선택 영역을 삭제 합니다.  
  
     자세한 내용은 참조 [끌어서 놓기 (OLE)](../mfc/drag-and-drop-ole.md)합니다.  
  
-   포함 된 개체 또는 조합 컨테이너/서버 응용 프로그램에 연결 되어 있습니다.  
  
     자세한 내용은 참조 [컨테이너: 고급 기능](../mfc/containers-advanced-features.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨테이너](../mfc/containers.md)   
 [컨테이너: 클라이언트 항목](../mfc/containers-client-items.md)

