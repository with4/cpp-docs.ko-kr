---
title: 이미지 목록의 이미지 오버레이 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55a55a6e015a2f8c1613a85717c030737712c4da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345409"
---
# <a name="image-overlays-in-image-lists"></a>이미지 목록의 이미지 오버레이
모든 이미지 목록 ([CImageList](../mfc/reference/cimagelist-class.md)) 오버레이 마스크도 사용할 이미지의 목록을 포함 합니다. "오버레이 마스크"에 다른 이미지 위에 투명 하 게 그려지는 하는 이미지입니다. 모든 이미지 오버레이 마스크도 사용할 수 있습니다. 이미지 목록 당 최대 4 개의 오버레이 마스크를 지정할 수 있습니다.  
  
 이미지의 인덱스를 사용 하 여 오버레이 마스크 목록에 추가 하면는 [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) 멤버 함수와 이미지의 인덱스 오버레이 마스크의 인덱스입니다. 참고는 오버레이 마스크에 대 한 인덱스는 1부터 시작 하지 않고 0부터 시작 합니다.  
  
 한 번 호출 하 여 이미지 위에 오버레이 마스크를 그릴 **그리기**합니다. 매개 변수를 그릴 이미지의 인덱스 및 오버레이 마스크의 인덱스에 포함 됩니다. 사용 해야 합니다는 [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) 매크로 오버레이 마스크의 인덱스를 지정 합니다. 호출할 때에 오버레이 이미지를 지정할 수는 [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CImageList 사용](../mfc/using-cimagelist.md)   
 [컨트롤](../mfc/controls-mfc.md)

