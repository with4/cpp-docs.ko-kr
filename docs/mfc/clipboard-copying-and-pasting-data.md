---
title: "클립보드: 데이터 복사 및 붙여넣기 | Microsoft Docs"
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
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6d76be3bd3863826391cc812f17dca88cb3a5457
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard-copying-and-pasting-data"></a>클립보드: 데이터 복사 및 붙여넣기
이 항목에서는에서 OLE 응용 프로그램에 클립보드에 복사 / 붙여넣기를 구현 하는 데 필요한 최소 작업에 설명 합니다. 읽는 것이 좋습니다.는 [데이터 개체 및 데이터 소스 (OLE)](../mfc/data-objects-and-data-sources-ole.md) 계속 진행 하기 전에 항목입니다.  
  
 복사 또는 붙여넣기를 구현할 수 있습니다, 전에 먼저 편집 메뉴에서 복사, 잘라내기 및 붙여넣기 옵션 처리할 함수를 제공 해야 합니다.  
  
##  <a name="_core_copying_or_cutting_data"></a>데이터 복사 또는 잘라내기  
  
#### <a name="to-copy-data-to-the-clipboard"></a>데이터를 클립보드에 복사 하려면  
  
1.  데이터를 복사는 네이티브 데이터 아니면 포함 또는 연결 된 항목 인지를 확인 합니다.  
  
    -   데이터를 포함 또는 연결 된 경우에 대 한 포인터를 얻을 `COleClientItem` 선택 된 개체입니다.  
  
    -   파생 된 새 개체를 만들 데이터는 네이티브 응용 프로그램 서버인 경우 `COleServerItem` 선택한 데이터가 들어 있는입니다. 그렇지 않으면 만듭니다는 `COleDataSource` 데이터에 대 한 개체입니다.  
  
2.  선택한 항목의 호출 `CopyToClipboard` 멤버 함수입니다.  
  
3.  사용자가 선택한 복사 작업을 대신 잘라내기 작업 하는 경우 응용 프로그램에서 선택한 데이터를 삭제 합니다.  
  
 이 시퀀스의 예를 보려면 참조는 **OnEditCut** 및 **OnEditCopy** 함수는 MFC OLE 샘플 프로그램 [OCLIENT](../visual-cpp-samples.md) 및 [HIERSVR](../visual-cpp-samples.md). 참고 1 단계 작업이 이미 완료 되므로 이러한 샘플 현재 선택 된 데이터에 대 한 포인터를 유지 합니다.  
  
##  <a name="_core_pasting_data"></a>데이터 붙여넣기  
 데이터 붙여넣기는에 응용 프로그램에 데이터를 붙여넣을 때 사용할 형식을 선택 해 서 복사할 때 보다 더 복잡 합니다.  
  
#### <a name="to-paste-data-from-the-clipboard"></a>클립보드의 데이터를 붙여 넣으려면  
  
1.  뷰 클래스에서 구현 **OnEditPaste** 편집 메뉴에서 붙여넣기 옵션을 선택 하는 사용자를 처리할 수 있습니다.  
  
2.  에 **OnEditPaste** 함수를 만들는 `COleDataObject` 개체와 호출 해당 `AttachClipboard` 멤버 함수를 클립보드에 데이터를이 개체에 연결 합니다.  
  
3.  호출 `COleDataObject::IsDataAvailable` 사용할 수 있는 특정 형식 인지 여부를 확인 합니다.  
  
     또는 사용할 수 있습니다 `COleDataObject::BeginEnumFormats` 응용 프로그램에 가장 적합 한 찾을 때까지 다른 형식에 대 한 조회 하 합니다.  
  
4.  서식의 붙여넣기를 수행 합니다.  
  
 이 과정의 예로의 구현을 참조는 **OnEditPaste** MFC OLE 샘플 프로그램에 정의 된 뷰 클래스의 멤버 함수 [OCLIENT](../visual-cpp-samples.md) 및 [HIERSVR](../visual-cpp-samples.md).  
  
> [!TIP]
>  분리 자체 함수로 붙여넣기 작업의 주요 장점은입니다 끌어서 놓기 작업 중 응용 프로그램에서 데이터를 삭제 하는 경우 동일한 붙여넣기 코드를 사용할 수 있습니다. OCLIENT 및 HIERSVR, 프로그램 `OnDrop` 함수를 호출할 수도 **DoPasteItem**, 붙여넣기 작업을 구현 하기 작성 된 코드를 다시 사용 합니다.  
  
 편집 메뉴에서 붙여넣기 옵션을 처리 하려면 항목을 참조 [OLE의 대화 상자](../mfc/dialog-boxes-in-ole.md)합니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [기타 서식 추가](../mfc/clipboard-adding-other-formats.md)  
  
-   [OLE 데이터 개체 및 데이터 원본 및 균일 한 데이터 전송](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE 끌어서 놓기](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## <a name="see-also"></a>참고 항목  
 [클립보드: OLE 클립보드 메커니즘 사용](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

