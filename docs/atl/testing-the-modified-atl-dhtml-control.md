---
title: "수정 된 ATL DHTML 컨트롤 테스트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c5ecb8526ec82e0f2d18c5306a94dd7f0160803b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="testing-the-modified-atl-dhtml-control"></a>수정 된 ATL DHTML 컨트롤 테스트
이제 작동 방식을 보려면 새 컨트롤을 사용해 봅니다.  
  
#### <a name="to-build-and-test-the-modified-control"></a>빌드 및 수정된 된 컨트롤을 테스트 하려면  
  
1.  프로젝트를 다시 작성 하 고 테스트 컨테이너에서 엽니다. 참조 [속성 및 이벤트 테스트 컨테이너와 테스트](../mfc/testing-properties-and-events-with-test-container.md) 테스트 컨테이너에 액세스 하는 방법에 대 한 합니다.  
  
     모든 추가 단추를 표시 하도록 컨트롤의 크기를 조정 합니다.  
  
2.  HTML을 변경 하 여 삽입 되는 두 개의 단추를 검사 합니다. 각 단추에서 확인 레이블 갖는 [ATL DHTML 컨트롤 수정](../atl/modifying-the-atl-dhtml-control.md): **새로 고침** 및 **HelloHTML**합니다.  
  
3.  두 개의 새 단추 컨트롤의 동작을 테스트 합니다.  
  
 이제 UI의 일부분이 아닌 메서드를 테스트 합니다.  
  
1.  테두리를 활성화 하도록 컨트롤을 강조 표시 합니다.  
  
2.  에 **제어** 메뉴를 클릭 하 여 **메서드 호출**합니다.  
  
 레이블이 지정 된 목록에 메서드 **메서드 이름** 컨테이너를 호출할 수 있는 방법이: `MethodInvoked` 및 `GoToURL`합니다. 다른 모든 메서드는 UI에 의해 제어 됩니다.  
  
1.  메서드를 호출 하 고 클릭 선택 `Invoke` 메서드의 메시지 상자를 표시 하거나 www.microsoft.com로 이동 합니다.  
  
2.  에 **메서드 호출** 대화 상자를 클릭 **닫기**합니다.  
  
 다양 한 요소와 ATL DHTML 컨트롤 구성 하는 파일에 대 한 자세한 참조 [DHTML 컨트롤 프로젝트의 요소를 식별](../atl/identifying-the-elements-of-the-dhtml-control-project.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DHTML 컨트롤에 대 한 지원](../atl/atl-support-for-dhtml-controls.md)

