---
title: '방법: 리본 컨트롤 및 이벤트 처리기 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 176323137b2ace0d27d9de162da7fa022441aa88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344421"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>방법: 리본 컨트롤 및 이벤트 처리기 추가
리본 메뉴 컨트롤은 단추와 콤보 상자 패널에 추가 하는 등의 요소입니다. 패널은 관련된 컨트롤의 그룹을 표시 하는 리본 표시줄의 영역입니다.  
  
 이 항목에서는 리본 디자이너를 열고, 단추를 추가 및 "Hello World"를 표시 하는 이벤트에 연결 하는 있습니다.  
  
### <a name="to-open-the-ribbon-designer"></a>리본 디자이너를 열려면  
  
1.  Visual Studio에서에 **보기** 메뉴를 클릭 하 여 **리소스 뷰**합니다.  
  
2.  **리소스 뷰**, 디자인 화면에 표시할 리본 리소스를 두 번 클릭 합니다.  
  
### <a name="to-add-a-button-and-an-event-handler"></a>단추 및 이벤트 처리기를 추가 하려면  
  
1.  **도구 모음**, 클릭 **단추** 디자인 화면에서 패널 위로 끌어 합니다.  
  
2.  단추를 마우스 오른쪽 단추로 클릭 하 고 클릭 **이벤트 처리기 추가**합니다.  
  
3.  에 **이벤트 처리기 마법사**기본 설정을 확인 하 고 클릭 **추가 및 편집**합니다. 자세한 내용은 참조 [이벤트 처리기 마법사](../ide/event-handler-wizard.md)합니다.  
  
4.  코드 편집기에서 다음 코드를 처리기 함수에 추가 합니다.  
  
 ```  
    MessageBox((LPCTSTR)L"Hello World");

 ```  
  
## <a name="see-also"></a>참고 항목  
 [RibbonGadgets 샘플: 리본 가젯 응용 프로그램](../visual-cpp-samples.md)   
 [리본 디자이너(MFC)](../mfc/ribbon-designer-mfc.md)

