---
title: "트리 컨트롤 항목 레이블 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d9baece3986b00aa2fbcea2b4b64217618834a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-item-labels"></a>트리 컨트롤 항목 레이블
트리 컨트롤에 항목을 추가할 때 일반적으로 항목의 레이블 텍스트를 지정 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). `InsertItem` 멤버 함수에 전달할 수는 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) 레이블의 텍스트를 포함 하는 문자열을 포함 하 여 항목의 속성을 정의 하는 구조입니다. `InsertItem`매개 변수를 다양 한 조합과 함께 호출 될 수 있는 몇 가지 오버 로드가 있습니다.  
  
 각 항목; 저장 하기 위한 메모리를 할당 하는 트리 컨트롤 항목 레이블 텍스트가이 메모리의 상당 부분을 차지합니다. 트리 컨트롤에서 문자열의 복사본을 유지 하는 응용 프로그램을 하는 경우 지정 하 여 컨트롤의 메모리 요구 사항을 줄일 수 있습니다는 **LPSTR_TEXTCALLBACK** 값에 **pszText** 의구성원`TV_ITEM` 또는 `lpszItem` 트리 컨트롤에 실제 문자열을 전달 하는 대신 매개 변수입니다. 사용 하 여 **LPSTR_TEXTCALLBACK** 트리 컨트롤을 항목을 그려야 할 때마다 응용 프로그램에서 항목의 레이블 텍스트를 검색 합니다. 텍스트를 검색 하려면 트리 컨트롤에서 전송 된 [TVN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) 의 주소를 포함 하는 알림 메시지는 [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) 구조입니다. 포함 된 구조체의 적절 한 멤버를 설정 하 여 응답 해야 합니다.  
  
 트리 컨트롤의 트리 컨트롤을 만드는 프로세스의 힙에서 할당 된 메모리를 사용 합니다. 트리 컨트롤에서 항목의 최대 수는 힙에서 사용 가능한 메모리 양에 기반으로 합니다. 각 항목에 64 바이트가 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

