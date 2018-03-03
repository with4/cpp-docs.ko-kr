---
title: "개별 항목에 대 한 이미지 설정 | Microsoft Docs"
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
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d9cb74c2290292f44b8c6c9b8797890e759f315
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="setting-the-images-for-an-individual-item"></a>개별 항목에 대한 이미지 설정
여러 종류의 확장 된 콤보 상자 항목에서 사용 하는 이미지의 값에 의해 결정 됩니다는 `iImage`, **iSelectedImage**, 및 **iOverlay** 의 멤버는 [COMBOBOXEXITEM ](http://msdn.microsoft.com/library/windows/desktop/bb775746) 구조입니다. 각 값은 컨트롤의 연결 된 이미지 목록의 이미지의 인덱스입니다. 기본적으로 이러한 멤버는 항목에 대 한 이미지가 표시 하도록 컨트롤을 일으키는 0으로 설정 됩니다. 특정 항목에 대 한 이미지를 사용 하려는 경우 수정할 수 있습니다 구조 적절 하 게 콤보 상자 항목을 삽입할 때 또는 기존 콤보 상자 항목을 수정 하 여 합니다.  
  
## <a name="setting-the-image-for-a-new-item"></a>새 항목에 대 한 이미지 설정  
 새 항목을 삽입 하는 경우 초기화는 `iImage`, **iSelectedImage**, 및 **iOverlay** 구조체 멤버를 적절 한 값으로 하 고 다음을 호출 하 여 항목을 삽입 [ CComboBoxEx::InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem)합니다.  
  
 다음 예제에서는 새 확장 된 콤보 상자 항목을 삽입 (`cbi`) 확장 된 콤보 상자 컨트롤에 (`m_comboEx`), 세 개 모두가 이미지 상태에 대해 인덱스를 제공 합니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]  
  
## <a name="setting-the-image-for-an-existing-item"></a>기존 항목에 대 한 이미지 설정  
 기존 항목을 수정 하는 경우 사용 해야 합니다는 **마스크** 의 멤버는 **COMBOBOXEXITEM** 구조입니다.  
  
#### <a name="to-modify-an-existing-item-to-use-images"></a>이미지를 사용 하려면 기존 항목을 수정 하려면  
  
1.  선언 된 **COMBOBOXEXITEM** 구조체이 고 설정는 **마스크** 수정에 관심이 있는 값에 데이터 멤버입니다.  
  
2.  이 구조를 사용 하 여에 대 한 호출을 내릴 [CComboBoxEx::GetItem](../mfc/reference/ccomboboxex-class.md#getitem)합니다.  
  
3.  수정 된 **마스크**, `iImage`, 및 **iSelectedImage** 적절 한 값을 사용 하 여 새로 반환 된 구조체의 멤버입니다.  
  
4.  호출할 [CComboBoxEx::SetItem](../mfc/reference/ccomboboxex-class.md#setitem)수정 된 구조에 전달 합니다.  
  
 다음 예제에서는 세 번째 확장 된 콤보 상자 항목의 또는 선택 하지 않은 이미지를 교체 하 여이 절차를 보여 줍니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CComboBoxEx 사용](../mfc/using-ccomboboxex.md)   
 [컨트롤](../mfc/controls-mfc.md)

