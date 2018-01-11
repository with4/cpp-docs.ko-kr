---
title: "이미지 목록 조작 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6c2670f3935e2f4c482728000a268cb46cc9dbdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="manipulating-image-lists"></a>이미지 목록 조작
[대체](../mfc/reference/cimagelist-class.md#replace) 이미지 목록의 이미지를 대체 하는 멤버 함수 ([CImageList](../mfc/reference/cimagelist-class.md))를 새 이미지로 합니다. 또한 이 기능은 이미지 목록 개체에서 이미지 수를 동적으로 늘려야 할 경우에 유용합니다. [SetImageCount](../mfc/reference/cimagelist-class.md#setimagecount) 함수는 이미지 목록에 저장 된 이미지의 수를 동적으로 변경 합니다. 이미지 목록의 크기를 늘리면 호출 **대체** 새 이미지 슬롯에 이미지 추가 합니다. 이미지 목록의 크기를 줄이면 새 크기를 넘어서는 이미지가 비워집니다.  
  
 [제거](../mfc/reference/cimagelist-class.md#remove) 멤버 함수는 이미지 목록에서 이미지를 제거 합니다. [복사](../mfc/reference/cimagelist-class.md#copy) 멤버 함수 복사 하거나 이미지 목록에 이미지를 교환할 수 있습니다. 이 함수에서는 소스 이미지를 대상 인덱스에 복사해야 하는지 또는 소스와 대상 이미지를 스왑해야 하는지를 나타낼 수 있습니다.  
  
 두 이미지 목록을 병합 하 여 새 이미지 목록을 만들려면 사용의 적합 한 오버 로드는 [만들기](../mfc/reference/cimagelist-class.md#create) 멤버 함수입니다. 이 오버 로드의 **만들기** 병합 기존 이미지의 첫 번째 이미지 목록에서 새 이미지 목록 개체에 결과 이미지를 저장 합니다. 새 이미지는 그리기로 생성되고, 두 번째 이미지는 첫 번째 이미지 위에 투명하게 표시됩니다. 새 이미지에 대한 마스크는 두 개의 기존 이미지에 대한 마스크의 비트에서 논리적 OR 연산을 수행한 결과입니다.  
  
 이 작업은 모든 이미지가 병합되고 새 이미지 목록 개체에 추가될 때까지 반복됩니다.  
  
 호출 하 여 보관 파일에 이미지 정보를 쓸 수는 [쓰기](../mfc/reference/cimagelist-class.md#write) 멤버 함수와 호출 하 여 다시 읽을 [읽기](../mfc/reference/cimagelist-class.md#read) 멤버 함수입니다.  
  
 [GetSafeHandle](../mfc/reference/cimagelist-class.md#getsafehandle), [연결](../mfc/reference/cimagelist-class.md#attach), 및 [분리](../mfc/reference/cimagelist-class.md#detach) 멤버 함수를 사용 하면에 연결 된 이미지 목록의 처리를 조작할 수는 `CImageList` 개체 동안는 [DeleteImageList](../mfc/reference/cimagelist-class.md#deleteimagelist) 멤버 함수를 삭제 하지 않고 이미지 목록을 삭제는 `CImageList` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CImageList 사용](../mfc/using-cimagelist.md)   
 [컨트롤](../mfc/controls-mfc.md)

