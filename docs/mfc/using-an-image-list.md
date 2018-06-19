---
title: 이미지 목록 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5722a2ef8c4e93e4996ee243b3c01b6dd6aeca78
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381607"
---
# <a name="using-an-image-list"></a>이미지 목록 사용
이미지 목록의 일반적인 사용 패턴을 따릅니다.  
  
-   생성 한 [CImageList](../mfc/reference/cimagelist-class.md) 개체와 호출의 오버 로드 중 하나는 [만들기](../mfc/reference/cimagelist-class.md#create) 이미지 목록을 만들고에 연결 하는 함수는 `CImageList` 개체입니다.  
  
-   이미지 목록을 만들 때 이미지를 추가 하지 않은 경우 이미지 목록에 추가할 이미지를 호출 하 여는 [추가](../mfc/reference/cimagelist-class.md#add) 또는 [읽기](../mfc/reference/cimagelist-class.md#read) 멤버 함수입니다.  
  
-   해당 컨트롤의 적절 한 멤버 함수를 호출 하 여 이미지 목록 컨트롤에 연결 하거나 이미지 목록을 사용 하 여 직접 이미지 목록에서 이미지를 그릴 [그리기](../mfc/reference/cimagelist-class.md#draw) 멤버 함수입니다.  
  
-   끌기를 위한 이미지 목록의 기본 제공 지원을 사용 하 여 이미지를 끌기 아마도 수 있습니다.  
  
> [!NOTE]
>  이미지 목록으로 만든 경우는 **새** destroy 합니다 연산자는 `CImageList` 을 마쳤을 때 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CImageList 사용](../mfc/using-cimagelist.md)   
 [컨트롤](../mfc/controls-mfc.md)

