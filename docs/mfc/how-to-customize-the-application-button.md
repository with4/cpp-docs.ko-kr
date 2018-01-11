---
title: "방법: 응용 프로그램 단추 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: application button [MFC], customizing
ms.assetid: ebb11180-ab20-43df-a234-801feca9eb38
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4a4a150985bd5c552b361620df87e34511ef8027
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-customize-the-application-button"></a>방법: 응용 프로그램 단추 사용자 지정
응용 프로그램 단추를 클릭할 때의 명령 메뉴에 표시 됩니다. 일반적으로 메뉴 명령이 포함 되어 파일 관련와 같은 **열려**, **저장**, **인쇄**, 및 **종료**합니다.  
  
 ![MFC 리본 응용 프로그램 단추](../mfc/media/application_button.png "application_button")  
  
 응용 프로그램 단추를 사용자 지정 하려면 열에 **속성** 창에서 해당 속성을 수정 하 고 다음 리본 컨트롤 미리 보기.  
  
### <a name="to-open-the-application-button-in-the-properties-window"></a>속성 창에서 응용 프로그램 단추를 열려면  
  
1.  Visual Studio에서에 **보기** 메뉴를 클릭 하 여 **리소스 뷰**합니다.  
  
2.  **리소스 뷰**, 디자인 화면에 표시할 리본 리소스를 두 번 클릭 합니다.  
  
3.  디자인 화면에서 응용 프로그램 단추 메뉴를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.  
  
## <a name="application-button-properties"></a>응용 프로그램 단추 속성  
 다음 표에서 응용 프로그램 단추의 속성을 정의 합니다.  
  
|속성|정의|  
|--------------|----------------|  
|**단추**|응용 프로그램 메뉴의 오른쪽 아래 모서리에 표시 되는 최대 3 개의 단추의 컬렉션을 포함 합니다.|  
|**캡션**|컨트롤의 텍스트를 지정합니다. 다른 리본 요소와는 달리 응용 프로그램 단추 캡션 텍스트를 표시 하지 않습니다. 대신, 텍스트 내게 필요한 옵션에 사용 됩니다.|  
|**HDPI Image**|(HDPI) 응용 프로그램 단추 아이콘 인치당 도트 높은의 식별자를 지정 합니다. 높은 DPI 모니터에서 응용 프로그램이 실행 될 때 **HDPI Image** 대신 사용 됩니다 **이미지**합니다.|  
|**HDPI Large Images**|높은 DPI 큰 이미지의 식별자를 지정 합니다. 높은 DPI 모니터에서 응용 프로그램이 실행 될 때 **HDPI Large Images** 대신 사용 됩니다 **큰 이미지**합니다.|  
|**HDPI Small Images**|높은 DPI 작은 이미지의 식별자를 지정 합니다. 높은 DPI 모니터에서 응용 프로그램이 실행 될 때 **HDPI Small Images** 대신 사용 됩니다 **작은 이미지**합니다.|  
|**ID**|컨트롤의 식별자를 지정합니다.|  
|**Image**|응용 프로그램 단추 아이콘의 식별자를 지정 합니다. 아이콘은 32 비트 26x26 비트맵 알파 투명도입니다. 아이콘의 투명 한 부분에는 응용 프로그램 단추를 클릭 하거나 위로 가져갈 때 강조 표시 됩니다.|  
|**키**|키 팁 탐색을 사용할 때 표시 되는 문자열을 지정 합니다. ALT 키를 키 팁 탐색을 사용할 수 있습니다.|  
|**큰 이미지**|일련의 32x32 아이콘을 포함 하는 이미지의 식별자를 지정 합니다. Main Items 컬렉션에 있는 단추가 아이콘이 사용 됩니다.|  
|**기본 항목**|응용 프로그램 메뉴에 나타나는 메뉴 항목의 컬렉션을 포함 합니다.|  
|**MRU Caption**|최근에 사용한 항목 목록 패널에 표시 되는 텍스트를 지정 합니다.|  
|**작은 이미지**|일련의 16 x 16 아이콘을 포함 하는 이미지의 식별자를 지정 합니다. 아이콘 단추 컬렉션에 있는 단추의 사용 됩니다.|  
|**사용 하 여**|최근에 사용한 항목 목록 패널을 사용 하지 않도록 설정 하거나 사용 합니다. 최근에 사용한 항목 목록 패널 응용 프로그램 메뉴에 나타납니다.|  
|**너비**|최근에 사용한 항목 목록 패널의 픽셀에서 너비를 지정합니다.|  
  
 응용 프로그램 메뉴는 디자인 화면에 나타나지 않습니다. 를 보려면 리본을 미리 볼 하거나 응용 프로그램을 실행 해야 합니다.  
  
#### <a name="to-preview-the-ribbon-control"></a>리본 컨트롤을 미리 보려면  
  
-   에 **Ribbon 편집기 도구 모음**, 클릭 **Ribbon 테스트**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [리본 디자이너(MFC)](../mfc/ribbon-designer-mfc.md)

