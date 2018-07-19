---
title: 목록 컨트롤 제거 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edb26671ba775cfa7daf98d39c7eccc9fd4111bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343284"
---
# <a name="destroying-the-list-control"></a>목록 컨트롤 제거
포함 한 경우 사용자 [CListCtrl](../mfc/reference/clistctrl-class.md) 뷰 또는 대화 상자 클래스의 데이터 멤버로 개체의 소유자가 소멸 될 때 소멸 됩니다. 사용 하는 경우는 [CListView](../mfc/reference/clistview-class.md), 보기를 제거 하는 경우 프레임 워크 컨트롤을 제거 합니다.  
  
 목록 컨트롤 아니라 응용 프로그램에 저장 될 목록 데이터 중 일부에 대해 정렬 하는 경우에 할당을 취소할 작업을 준비 해야 합니다. 자세한 내용은 참조 [콜백 항목 및 콜백 마스크](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows sdk에서입니다.  
  
 또한 모든 이미지 목록을 만들고 list 컨트롤 개체와 연결 된 할당 해제 하는 일을 담당 하 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

