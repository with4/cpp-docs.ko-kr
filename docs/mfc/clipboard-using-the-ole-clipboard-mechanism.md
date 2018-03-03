---
title: "클립보드: OLE 클립보드 메커니즘 사용 | Microsoft Docs"
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
- applications [OLE], Clipboard
- OLE Clipboard
- Clipboard [MFC], OLE formats
- OLE Clipboard, formats
- formats [MFC], Clipboard for OLE
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4996c6559ad20141fb84ed37e87fd1551e89a77b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard-using-the-ole-clipboard-mechanism"></a>클립보드: OLE 클립보드 메커니즘 사용
OLE는 클립보드를 통해 데이터를 전송 하기 위한 표준 형식 및 몇 가지 특정 형식을 사용 합니다.  
  
 잘라내거나 응용 프로그램에서 데이터를 복사할 때 데이터 붙여넣기 작업에서 나중에 사용할를 클립보드에 저장 됩니다. 이 데이터는 다양 한 형식입니다. 클립보드의 데이터를 선택할 경우 응용 프로그램 이러한 형식을 사용 중 선택할 수 있습니다. 요청 하지 않으면 사용자 특히 특정 형식으로 선택 하 여 붙여넣기를 사용 하 여 대부분의 정보를 제공 하는 형식을 선택 하는 응용 프로그램을 작성 되어야 합니다. 계속 하기 전에 만들려는 경우 읽기는 [데이터 개체 및 데이터 소스 (OLE)](../mfc/data-objects-and-data-sources-ole.md) 항목입니다. 응용 프로그램에 구현 하는 방법 및 데이터 작업을 전송 하는 방법을의 기본적인 사항을 설명 합니다.  
  
 Windows에는 여러 가지 클립보드를 통해 데이터를 전송 하는 데 사용할 수 있는 표준 형식 정의 합니다. 여기에 메타 파일, 텍스트, 비트맵 및 기타 포함 됩니다. OLE는 다양 한 특정 형식으로 정의합니다. 이 표준 형식으로 지정 된 것 보다 더 자세한 정보를 필요로 하는 응용 프로그램의 경우 자신의 사용자 지정 클립보드 형식을 등록 하 것이 좋습니다. Win32 API 함수를 사용 하 여 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 에이 작업을 수행 합니다.  
  
 예를 들어 Microsoft Excel 스프레드시트에 대 한 사용자 지정 형식을 등록합니다. 이 형식 보다 훨씬 더 많은 정보를 전달, 비트맵입니다. 응용 프로그램을 지 원하는 스프레드시트 형식으로이 데이터를 붙여 넣은 모든 수식 및 스프레드시트에서 값은 보존 되 고 필요한 경우 업데이트 됩니다. OLE 항목으로 붙여 넣을 수 있도록 형식으로 클립보드에 데이터가 또한 저장 합니다. 모든 OLE 문서 컨테이너에는이 정보 포함된 된 항목으로 붙여 넣을 수 있습니다. Microsoft Excel을 사용 하 여이 포함 된 항목을 변경할 수 있습니다. 클립보드에 다음은 스프레드시트에서 선택한 범위 이미지의 간단한 비트맵 포함 되어 있습니다. 이 또한 붙여 넣을 수 OLE 문서 컨테이너 또는 페인트 같은 비트맵 편집기입니다. 그러나 비트맵의 경우 방법이 있으면 스프레드시트로 데이터를 조작 합니다.  
  
 클립보드에서 최대한의 정보를 검색 하려면 응용 프로그램 데이터를 클립보드에서 붙여넣기 전에이 사용자 지정 형식을 확인 해야 합니다.  
  
 예를 들어 잘라내기 명령을 사용 하려면 작성할 수 있습니다는 처리기 다음과 같습니다.  
  
 [!code-cpp[NVC_MFCListView#3](../atl/reference/codesnippet/cpp/clipboard-using-the-ole-clipboard-mechanism_1.cpp)]  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [데이터 복사 및 붙여넣기](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [기타 서식 추가](../mfc/clipboard-adding-other-formats.md)  
  
-   [Windows 클립보드 사용](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
-   [OLE 데이터 개체 및 데이터 원본 및 균일 한 데이터 전송](../mfc/data-objects-and-data-sources-ole.md)  
  
## <a name="see-also"></a>참고 항목  
 [클립보드](../mfc/clipboard.md)

