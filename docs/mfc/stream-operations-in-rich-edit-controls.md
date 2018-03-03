---
title: "Rich Edit 컨트롤의 작업 스트림 | Microsoft Docs"
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
- CRichEditCtrl class [MFC], stream operations
- CRichEditCtrl class [MFC], stream storage
- rich edit controls [MFC], stream operations
- storage, stream in CRichEditCtrl
- stream operations in CRichEditCtrl
- stream storage and CRichEditCtrl
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1a73790124adbc1ff8a89290bf4e1d7a4fa6824
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stream-operations-in-rich-edit-controls"></a>Rich Edit 컨트롤의 스트림 작업
Rich edit 컨트롤 안팎으로 데이터를 전송 하도록 스트림을 사용할 수 있습니다 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). 스트림을 정의한는 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) 버퍼 및 응용 프로그램에서 정의 된 콜백 함수를 지정 하는 구조입니다.  
  
 읽을 데이터를 서식 편집 컨트롤 (즉, 스트림 데이터를) 사용 하 여는 [StreamIn](../mfc/reference/cricheditctrl-class.md#streamin) 멤버 함수입니다. 컨트롤이 응용 프로그램에서 정의된 콜백 함수를 반복적으로 호출하여 매번 데이터의 일부를 버퍼로 전송합니다.  
  
 저장 하려면 내용의 rich edit 컨트롤 (즉, 데이터 스트림 아웃)를 사용할 수 있습니다는 [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) 멤버 함수입니다. 컨트롤이 버퍼에 쓰기를 반복한 후 응용 프로그램에서 정의된 콜백 함수를 호출합니다. 각 호출마다 콜백 함수는 버퍼 내용을 저장합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

