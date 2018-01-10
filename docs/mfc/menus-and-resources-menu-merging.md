---
title: "메뉴 및 리소스: 메뉴 병합 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- coordinating menu layouts [MFC]
- OLE containers [MFC], menus and resources
- toolbars [MFC], OLE document applications
- merging toolbar and status bar [MFC]
- menus [MFC], OLE document applications
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c686d461a3052feb4a55cf7948b58102f10ac1f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="menus-and-resources-menu-merging"></a>메뉴 및 리소스: 메뉴 병합
이 문서는 OLE 문서 응용 프로그램에서 내부 활성화 제대로 비주얼 편집을 처리 하는 데 필요한 단계를 설명 합니다. 내부 활성화 사용 하는 경우 컨테이너와 서버 모두에 대 한 응용 프로그램 (구성 요소). 사용자 (컨테이너 문서의 컨텍스트) 내에서 동일한 프레임 창에 남아 있지만 실제로 다른 응용 프로그램 (서버)를 실행 합니다. 이 컨테이너 및 서버 응용 프로그램의 리소스 간에 조정을 해야합니다.  
  
 이 문서에서 다루는 항목은 다음과 같습니다.  
  
- [메뉴 레이아웃](#_core_menu_layouts)  
  
- [도구 모음 및 상태 표시줄](#_core_toolbars_and_status_bars)  
  
##  <a name="_core_menu_layouts"></a>메뉴 레이아웃  
 메뉴 레이아웃을 조정 하는 첫 번째 단계가입니다. 자세한 내용은 참조는 **메뉴 만들기** 섹션 [메뉴 프로그래밍 고려 사항](https://msdn.microsoft.com/library/ms647557.aspx) Windows sdk에서입니다.  
  
 컨테이너 응용 프로그램 내부에서 포함 된 항목은 활성화 하는 경우에 사용할 수 있는 새 메뉴를 만들어야 합니다. 이 메뉴에는 최소한 나열 된 순서로 다음으로 구성 되어야:  
  
1.  파일이 열려 있는 경우 사용 하는 것과 동일한 파일 메뉴. (일반적으로 메뉴 항목이 없습니다 사항이 다음 항목 앞.)  
  
2.  두 개의 연속 된 구분 기호입니다.  
  
3.  파일이 열려 있는 경우 사용 하는 것과 동일한 창 메뉴 (경우에만 MDI 응용 프로그램 컨테이너 응용 프로그램). 일부 응용 프로그램에 포함된 된 항목은 현재 위치에서 활성화 될 때 메뉴에 유지 되는이 그룹에 속하는 옵션 메뉴와 같은 다른 메뉴가 있을 수 있습니다.  
  
    > [!NOTE]
    >  확대/축소와 같은 컨테이너 문서의 보기에 영향을 주는 다른 메뉴 있을 수 있습니다. 이러한 컨테이너 메뉴가 메뉴 리소스에서 두 개의 구분 기호 사이 나타납니다.  
  
 서버 (구성 요소) 응용 프로그램에 새 메뉴에는 내부 활성화에 맞게 만들어야 합니다. 파일을 열 때 사용 되는 메뉴 하지만 파일 및 데이터 대신 서버 문서를 조작 하는 창과 같은 새 메뉴 항목 이어야 합니다. 일반적으로 다음으로 구성이 됩니다.  
  
1.  파일이 열려 있는 경우 사용 하는 것과 동일한 메뉴를 편집 합니다.  
  
2.  구분선입니다.  
  
3.  편집 메뉴 Scribble 샘플 응용 프로그램에서 펜 메뉴와 같은 개체입니다.  
  
4.  구분선입니다.  
  
5.  도움말 메뉴.  
  
 예를 들어 일부 샘플 내부 메뉴 컨테이너와 서버에 대 한 레이아웃을 살펴봅니다. 각 메뉴 항목의 내용은 예 더 명확 하 게 제거 되었습니다. 컨테이너의 내부 메뉴에는 다음과 같은 항목이 있습니다.  
  
```  
IDR_CONTAINERTYPE_CNTR_IP MENU PRELOAD DISCARDABLE   
BEGIN  
    POPUP "&File C1"  
    MENUITEM SEPARATOR  
    POPUP "&Zoom C2"  
    MENUITEM SEPARATOR  
    POPUP "&Options C3"  
    POPUP "&Window C3"  
END  
```  
  
 연속 된 구분 기호는 서버 메뉴의 첫 번째 부분 이동 해야을 나타냅니다. 이제는 서버 내부에서 메뉴에 표시 됩니다.  
  
```  
IDR_SERVERTYPE_SRVR_IP MENU PRELOAD DISCARDABLE   
BEGIN  
    POPUP "&Edit S1"  
    MENUITEM SEPARATOR  
    POPUP "&Format S2"  
    MENUITEM SEPARATOR  
    POPUP "&Help S3"  
END  
```  
  
 여기에서 구분 기호는 두 번째 그룹 컨테이너 메뉴 항목을 이동 해야 나타냅니다. 이 컨테이너 내부에서이 서버에서 개체 활성화 될 때 결과 메뉴 구조는 다음과 같습니다.  
  
```  
BEGIN  
    POPUP "&File C1"  
    POPUP "&Edit S1"  
    POPUP "&Zoom C2"  
    POPUP "&Format S2"  
    POPUP "&Options C3  
    POPUP "&Window C3"  
    POPUP "&Help S3"  
END  
```  
  
 볼 수 있듯이 각 응용 프로그램의 메뉴의 다른 그룹과 구분 기호 대체 되었습니다.  
  
 액셀러레이터 키 테이블 내부 메뉴와 연결 된 서버 응용 프로그램에 의해 제공 되어야 합니다. 컨테이너 자체 액셀러레이터 키 테이블 통합 하 여 합니다.  
  
 포함된 된 항목에에서 활성화 되 면 프레임 워크 내부 메뉴를 로드 합니다. 서버 응용 프로그램에 내부 활성화를 요청 하 고 구분 기호는 위치에 삽입 합니다. 메뉴 결합 하는 방법을입니다. 메뉴 컨테이너에서 파일 및 창 배치에 대해 작업 만들어지고 해당 항목을 작동 하는 것에 대 한 서버에서 메뉴를 가져옵니다.  
  
##  <a name="_core_toolbars_and_status_bars"></a>도구 모음 및 상태 표시줄  
 서버 응용 프로그램 도구 모음을 새로 만들고 해당 비트맵 별도 파일에 저장 해야 합니다. 이 비트맵 ITOOLBAR 라는 파일에 저장 하는 응용 프로그램 마법사에서 생성 된 응용 프로그램입니다. BMP 합니다. 새 도구 모음에서 서버 항목이 장소에서 활성화 되 고 해야 하면 일반 도구 모음과 동일한 항목을 포함 하지만 파일 및 창 메뉴에 있는 항목을 나타내는 아이콘은 제거 컨테이너 응용 프로그램의 도구 모음을 대체 합니다.  
  
 이 도구 모음에 로드 될 프로그램 `COleIPFrameWnd`-응용 프로그램 마법사에서 만든 클래스를 파생 합니다. 상태 표시줄 컨테이너 응용 프로그램에서 처리 됩니다. 내부 프레임 창 구현에 대 한 자세한 내용은 참조 하십시오. [서버: 서버 구현](../mfc/servers-implementing-a-server.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메뉴 및 리소스 (OLE)](../mfc/menus-and-resources-ole.md)   
 [정품 인증](../mfc/activation-cpp.md)   
 [서버](../mfc/servers.md)   
 [컨테이너](../mfc/containers.md)

