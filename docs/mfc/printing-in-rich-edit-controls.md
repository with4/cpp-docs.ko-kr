---
title: "Rich Edit 컨트롤의 인쇄 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab8e15e25e2d419bb7c3ac67fc2c6f3453fb03c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="printing-in-rich-edit-controls"></a>Rich Edit 컨트롤의 인쇄
Rich edit 컨트롤을 확인할 수 있습니다 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 프린터와 같은 지정 된 장치에 대 한 해당 출력을 렌더링 합니다. 출력 장치 rich edit 컨트롤의 텍스트 서식을 지정할 수 있습니다.  
  
 부분에서는 특정 장치에 대 한 서식 있는 편집 컨트롤의 내용에 서식을 지정 하려면 사용할 수 있습니다는 [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange) 멤버 함수입니다. [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) 이 함수를 사용 하는 구조 대상 장치에 대 한 디바이스 컨텍스트 (DC) 뿐 아니라 서식을 지정 하려면 텍스트의 범위를 지정 합니다.  
  
 출력 장치에 대 한 텍스트를 포맷 한 후 보낼 수 있습니다 출력 장치에 사용 하 여는 [DisplayBand](../mfc/reference/cricheditctrl-class.md#displayband) 멤버 함수입니다. 반복 해 서 사용 하 여 `FormatRange` 및 `DisplayBand`, 서식 있는 편집 컨트롤의 내용을 인쇄 하는 응용 프로그램에서 밴드를 구현할 수 있습니다. (밴드는 출력의 더 작은 부분으로 나누기 인쇄용.)  
  
 사용할 수는 [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice) rich edit 컨트롤 대상 장치를 지정 하려면 멤버 함수는 텍스트 형식으로 변환 합니다. (표시 결과가)이이 함수는 WYSIWYG에 유용 서식, 응용 프로그램 기본 프린터의 글꼴 메트릭 화면의 대신 사용 하 여 텍스트 배치입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

