---
title: "확장 된 콤보 상자 컨트롤에서 이미지 목록 사용 | Microsoft Docs"
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
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ac69e7d0dbe1748a409b107579c747b7f9a4a7c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>확장 콤보 상자 컨트롤에서 이미지 목록 사용
확장 된 콤보 상자 컨트롤의 주요 기능은는 콤보 상자 컨트롤의 개별 항목과 함께 이미지 목록의 이미지를 연결 하는 기능입니다. 각 항목은 세 가지 서로 다른 이미지를 표시할 수 있으며: 선택 된 상태로, 오버레이 이미지에 대 한 세 번째 이와 선택 되지 않은 상태에 대 한 하나 있습니다.  
  
 다음 절차는 확장 된 콤보 상자 컨트롤 이미지 목록에 연결:  
  
### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>확장 된 콤보 상자 컨트롤과 함께 이미지 목록을 연결 하려면  
  
1.  새 이미지 목록을 생성 (또는 기존 이미지 목록 개체를 사용 하 여)를 사용 하는 [CImageList](../mfc/reference/cimagelist-class.md) 생성자 및 결과 포인터를 저장 합니다.  
  
2.  호출 하 여 새 이미지 목록 개체를 초기화 [CImageList::Create](../mfc/reference/cimagelist-class.md#create)합니다. 다음 코드는이 호출의 한 가지 예입니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]  
  
3.  가능한 각 상태에 대 한 선택적 이미지 추가: 선택한 및 또는, 선택 되지 않은 오버레이입니다. 다음 코드는 세 개의 미리 정의 된 이미지를 추가 합니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]  
  
4.  호출 하 여 컨트롤과 함께 이미지 목록을 연결 [CComboBoxEx::SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist)합니다.  
  
 이미지 목록 컨트롤에 연결 된 되 면 각 항목의 세 가지 가능한 상태에 사용할 이미지를 개별적으로 지정할 수 있습니다. 자세한 내용은 참조 [개별 항목에 대 한 이미지 설정](../mfc/setting-the-images-for-an-individual-item.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComboBoxEx 사용](../mfc/using-ccomboboxex.md)   
 [컨트롤](../mfc/controls-mfc.md)

