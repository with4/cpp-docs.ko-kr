---
title: "메뉴 및 리소스: 서버 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDP_OLE_INIT_FAILED
dev_langs: C++
helpviewer_keywords:
- OLE visual editing servers [MFC]
- accelerator tables [MFC], server applications
- visual editing [MFC], application menus and resources
- server applications [MFC], accelerator table
- string tables [MFC], visual editing applications
- servers [MFC], menu additions
- resources [MFC], server applications
- OLE server applications [MFC], menus and resources
- string editing [MFC], visual editing applications
- IDP_OLE_INIT_FAILED macro [MFC]
- server applications [MFC], OLE menus and resources
- OLE initialization failure [MFC]
ms.assetid: 56ce9e8d-8f41-4db8-8dee-e8b0702d057c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c7aaf4a087fbcfc28686e7ec8d2411d6f7531466
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="menus-and-resources-server-additions"></a>메뉴 및 리소스: 서버 추가
이 문서에서는 메뉴 및 비주얼 편집 서버 (구성 요소) 응용 프로그램의 다른 리소스에 적용 하는 변경 사항을 설명 합니다. 세 가지 모드 중 하나에서 시작 하려면 때문에 서버 응용 프로그램의 메뉴 구조 및 기타 리소스에 많은 추가 필요: 독립 실행형 모드, 포함 또는 위치에 있습니다. 에 설명 된 대로 [메뉴 및 리소스 (OLE)](../mfc/menus-and-resources-ole.md) 문서, 4 개의 집합이 메뉴의 최대는 합니다. 4는 3 개만 모드만 사용 되지만 MDI 풀 서버 응용 프로그램에 사용 됩니다. 응용 프로그램 마법사에서는 원하는 서버 유형에 필요한 메뉴 레이아웃을 만듭니다. 일부 사용자 지정을 할 수 있습니다.  
  
 응용 프로그램 마법사를 사용 하지 않는 경우에 HIERSVR 확인 하는 것이 좋습니다. RC, MFC 샘플 응용 프로그램에 대 한 리소스 스크립트 [HIERSVR](../visual-cpp-samples.md)이러한 변경 내용을 구현 하는 방법을 참조 하십시오.  
  
 이 문서에서 다루는 항목은 다음과 같습니다.  
  
-   [서버 메뉴 추가](#_core_server_menu_additions)  
  
-   [액셀러레이터 키 테이블 추가](#_core_server_application_accelerator_table_additions)  
  
-   [문자열 테이블 추가](../mfc/menus-and-resources-container-additions.md)  
  
-   [미니 서버 추가](#_core_mini.2d.server_additions)  
  
##  <a name="_core_server_menu_additions"></a>서버 메뉴 추가  
 서버 (구성 요소) 응용 프로그램 메뉴 리소스 OLE 비주얼 편집을 지원 하기 위해 추가 되어 있어야 합니다. 응용 프로그램은 독립 실행형 모드에서 실행 될 때 사용 하는 메뉴 변경할 필요는 없지만 응용 프로그램을 빌드하기 전에 두 가지 새 메뉴 리소스를 추가 해야 합니다: 완전 개방 되 고 서버를 지원 하기 이전과 내부 활성화를 지원 하도록 하나 있습니다. 전체 및 미니 서버 응용 프로그램에서 메뉴 리소스가 모두 사용 됩니다.  
  
-   내부 활성화를 지원 하려면 메뉴 리소스 매우 비슷하지만 독립 실행형 모드에서 실행할 때 사용 되는 메뉴 리소스를 만들어야 합니다. 이 메뉴의 차이 파일 및 창 항목 (및 응용 프로그램 및 데이터를 처리 하는 다른 모든 메뉴 항목)를 없습니다. 컨테이너 응용 프로그램에서 이러한 새 메뉴 항목을 제공 합니다. 이 메뉴 병합 하는 방법의 예제와 자세한 정보에 대 한 문서를 참조 [메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md)합니다.  
  
-   완전 개방 활성화를 지원 하려면 독립 실행형 모드에서 실행할 때 메뉴 리소스 거의 동일한 사용 되는 메뉴 리소스를 만들어야 합니다. 이 메뉴 리소스에만 수정은 복합 문서에 포함 된 항목에는 서버가 작동 한다는 사실을 반영 하기 위해 일부 항목은 다시 표시 된입니다.  
  
 이 문서에 나열 된 변경 내용을 외에도 다음 리소스 파일 AFXOLESV 포함 해야 합니다. Microsoft Foundation Class 라이브러리 구현에 필요한 RC 이 파일은 MFC\Include 하위 디렉터리에 있습니다.  
  
##  <a name="_core_server_application_accelerator_table_additions"></a>서버 응용 프로그램 액셀러레이터 키 테이블 추가  
 두 개의 새 액셀러레이터 키 테이블 리소스는 서버 응용 프로그램에 추가 되어야 합니다. 앞에서 설명한 새로운 메뉴 리소스에 직접 해당 합니다. 첫 번째 액셀러레이터 키 테이블에는 서버 응용 프로그램 내부에서 활성화 될 때 사용 됩니다. 파일 및 창에 연결 된 메뉴 점을 제외 하 고 보기의 액셀러레이터 키 테이블에 있는 모든 항목의 구성 됩니다.  
  
 두 번째 테이블은 거의 보기의 액셀러레이터 키 테이블의 정확한 복사본입니다. 모든 차이점에 언급 된 완전히 열기 메뉴에서 변경 내용을 병렬 [서버 메뉴 추가](#_core_server_menu_additions)합니다.  
  
 이러한 액셀러레이터 키 테이블 변경의 예로에 대 한 비교는 **IDR_HIERSVRTYPE_SRVR_IP** 및 **IDR_HIERSVRTYPE_SRVR_EMB** 가속기가 포함 된 테이블 **IDR_MAINFRAME** HIERSVR에서. MFC OLE 샘플에 포함 된 RC 파일과 [HIERSVR](../visual-cpp-samples.md)합니다. 파일 및 Window 액셀러레이터 내부 테이블에서 누락 되어 정확한 사본을 포함 된 테이블에 있습니다.  
  
##  <a name="_core_string_table_additions_for_server_applications"></a>서버 응용 프로그램에 대 한 문자열 테이블 추가  
 하나의 문자열 테이블에 추가 서버 응용 프로그램에 필요-는 문자열을 나타내는 OLE를 초기화 하지 못했습니다. 예를 들어, 응용 프로그램 마법사에서 생성 하는 문자열 테이블 항목 다음과 같습니다.  
  
|ID|문자열|  
|--------|------------|  
|**IDP_OLE_INIT_FAILED**|OLE 초기화 하지 못했습니다. OLE 라이브러리 버전이 올바른지 확인 합니다.|  
  
##  <a name="_core_mini.2d.server_additions"></a>미니 서버 추가  
 동일한 추가 적용으로 위에 나열 된 미니 서버 전체에 대 한 합니다. 미니를 독립 실행형 모드에서 실행할 수 없습니다. 때문에 주 메뉴는 훨씬 더 작습니다. 응용 프로그램 마법사로 만든 주 메뉴에만 파일을 포함 하는 메뉴가 종료 항목만 및 약 합니다. 포함 및 내부 메뉴 및 액셀러레이터 미니 서버 전체에 대 한 것과 동일합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메뉴 및 리소스 (OLE)](../mfc/menus-and-resources-ole.md)   
 [메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md)

