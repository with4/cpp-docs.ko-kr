---
title: 이미지 목록과 Rebar 컨트롤 함께 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f902cb24d5cd8525a99f58fc5feeac416138148
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381747"
---
# <a name="using-an-image-list-with-a-rebar-control"></a>이미지 목록과 Rebar 컨트롤 함께 사용
각 rebar 밴드는 특히 연결된 이미지 목록의 이미지를 포함할 수 있습니다. 다음 절차는 rebar 밴드에서 이미지를 표시하는 데 필요한 단계를 자세히 설명합니다.  
  
### <a name="to-display-images-in-a-rebar-band"></a>rebar 밴드에서 이미지를 표시하려면  
  
1.  호출 하 여 이미지 목록을 rebar 컨트롤 개체에 연결 [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist), 기존 이미지 목록에 대 한 포인터를 전달 합니다.  
  
2.  수정 된 **REBARBANDINFO** 이미지를 rebar 밴드에 할당 하는 구조:  
  
    -   설정의 **fMask** 멤버 **RBBIM_IMAGE**, 비트 OR 연산자를 사용 하 여 필요에 따라 추가 플래그를 포함 하도록 합니다.  
  
    -   `iImage` 멤버를 표시될 이미지의 이미지 목록 인덱스로 설정합니다.  
  
3.  필요한 정보를 사용하여 자식 창을 포함하는 핸들과 텍스트, 크기와 같은 나머지 모든 데이터 멤버를 초기화합니다.  
  
4.  호출 하 여 새 밴드 (이미지)와 함께 삽입 [CReBarCtrl::InsertBand](../mfc/reference/crebarctrl-class.md#insertband)전달 하는 **REBARBANDINFO** 구조입니다.  
  
 다음 예제에서는 두 개의 이미지가 있는 기존 이미지 목록 개체가 rebar 컨트롤 개체(`m_wndReBar`)에 연결되어 있다고 가정합니다. 첫 번째 이미지를 포함하는 새 rebar 밴드(`rbi`로 정의됨)는 `InsertBand`에 대한 호출로 추가됩니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CReBarCtrl 사용](../mfc/using-crebarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

