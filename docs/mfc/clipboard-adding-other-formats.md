---
title: '클립보드: 기타 서식 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67004ac43193d47720626da241a8030ba396abdf
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932021"
---
# <a name="clipboard-adding-other-formats"></a>클립보드: 기타 서식 추가
이 항목에서는 특히 OLE 지원에 대 한 지원 되는 형식 목록을 확장 하는 방법을 설명 합니다. 항목 [클립보드: 데이터 복사 및 붙여 넣으십시오](../mfc/clipboard-copying-and-pasting-data.md) 클립보드에서 복사 / 붙여넣기를 지 원하는 데 필요한 최소 구현에 설명 합니다. 클립보드에 복사 하는 유일한 형식은 이것이 구현할 모든 이면 **CF_METAFILEPICT**, **CF_EMBEDSOURCE**, **CF_OBJECTDESCRIPTOR**, 해야 했으며 **CF_LINKSOURCE**합니다. 대부분의 응용 프로그램에는이 세 가지 보다 클립보드에 많은 서식이 필요 합니다.  
  
##  <a name="_core_registering_custom_formats"></a> 사용자 지정 형식 등록  
 모든 사용자 지정 클립보드 형식을 등록 하는 경우 사용 동일한 절차에 따라 사용자 지정 서식을 만들려면: 형식 사용 하 여의 이름을 전달 하는 **됩니다** 함수 사용 하 고 해당 반환 값으로 id 형식입니다.  
  
##  <a name="_core_placing_formats_on_the_clipboard"></a> 클립보드에 형식 추가  
 더 많은 형식에 클립보드에 복사 하는 것을 추가 하려면 재정의 해야 합니다는 `OnGetClipboardData` 함수 중 하나에서 파생 된 클래스에서 `COleClientItem` 또는 `COleServerItem` (인지에 따라 데이터를 복사 전용). 이 함수에서 다음 절차를 사용 해야 합니다.  
  
#### <a name="to-place-formats-on-the-clipboard"></a>클립보드에 형식을 추가 하려면  
  
1.  `COleDataSource` 개체를 만듭니다.  
  
2.  이 데이터 소스를 호출 하 여 네이티브 데이터 형식을 지원 되는 형식 목록에 추가 하는 함수에 전달할 `COleDataSource::CacheGlobalData`합니다.  
  
3.  표준 형식을 호출 하 여 추가 `COleDataSource::CacheGlobalData` 지원 하려는 각 표준 형식에 대 한 합니다.  
  
 이 방법은 MFC OLE 샘플 프로그램에 사용 됩니다 [HIERSVR](../visual-cpp-samples.md) (검사는 `OnGetClipboardData` 의 멤버 함수는 **CServerItem** 클래스). 이 샘플에서 유일한 차이점은 해당 단계 3 HIERSVR 표준 없는 다른 형식을 지원 하기 때문에 구현 되지 않았습니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [OLE 데이터 개체 및 데이터 원본 및 균일 한 데이터 전송](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE 끌어서 놓기](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## <a name="see-also"></a>참고 항목  
 [클립보드: OLE 클립보드 메커니즘 사용](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

