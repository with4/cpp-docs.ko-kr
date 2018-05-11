---
title: 단일 문서에 뷰 여러 개 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb40b356b5601e19c33083c7b731a1dc411de3c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="adding-multiple-views-to-a-single-document"></a>단일 문서에 뷰 여러 개 추가
Microsoft Foundation 클래스 (MFC) 라이브러리를 사용 하 여 만든 단일 문서 인터페이스 (SDI) 응용 프로그램에서는 각 문서 형식은 단일 보기 형식과 연결 됩니다. 경우에 따라 새 보기와 문서를 현재 보기를 전환 하는 기능이 하는 것이 좋습니다.  
  
> [!TIP]
>  단일 문서에 대 한 여러 뷰를 구현에 추가 절차를 참조 하십시오. [CDocument::AddView](../mfc/reference/cdocument-class.md#addview) 및 [수집](../visual-cpp-samples.md) MFC 샘플.  
  
 추가 하 여이 기능을 구현할 수 `CView`-파생 된 클래스 및 기존 MFC 응용 프로그램에 보기를 동적으로 전환 하기 위한 코드를 추가 합니다.  
  
 단계는 다음과 같습니다.  
  
-   [기존 응용 프로그램 클래스를 수정 합니다.](#vcconmodifyexistingapplicationa1)  
  
-   [만들고 새 뷰 클래스를 수정 합니다.](#vcconnewviewclassa2)  
  
-   [만들고 연결 하려면 새 보기](#vcconattachnewviewa3)  
  
-   [전환 함수 구현](#vcconswitchingfunctiona4)  
  
-   [뷰를 전환에 대 한 지원 추가](#vcconswitchingtheviewa5)  
  
 이 항목의 나머지 부분에서는 다음을 가정합니다.  
  
-   이름을 `CWinApp`-파생 된 개체는 `CMyWinApp`, 및 `CMyWinApp` 선언 되 고 MYWINAPP에 정의 합니다. H와 MYWINAPP 합니다. CPP 합니다.  
  
-   `CNewView` 새 이름인 `CView`-파생 개체를 및 `CNewView` 선언 되 고 새 보기에 정의 합니다. 새 보기를 H. CPP 합니다.  
  
##  <a name="vcconmodifyexistingapplicationa1"></a> 기존 응용 프로그램 클래스를 수정 합니다.  
 보기 간 전환을 하려면 응용 프로그램에 대 한 뷰와 전환 하는 메서드를 저장 하려면 멤버 변수를 추가 하 여 응용 프로그램 클래스를 수정 해야 합니다.  
  
 선언에 다음 코드를 추가 `CMyWinApp` MYWINAPP에 있습니다. H:  
  
 [!code-cpp[NVC_MFCDocViewSDI#1](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]  
  
 새 멤버 변수 `m_pOldView` 및 `m_pNewView`, 현재 보기와 새로 만든된 것을 가리킵니다. 새 메서드 (`SwitchView`) 사용자가 요청 하는 경우 보기를 전환 합니다. 메서드의 본문에이 항목 뒷부분에서 설명 [전환 기능을 구현](#vcconswitchingfunctiona4)합니다.  
  
 Windows 메시지를 정의 하는 새 헤더 파일을 포함 하 여 응용 프로그램 클래스에 마지막으로 수정한 필요 (**WM_INITIALUPDATE**) 전환 함수에 사용 되는 합니다.  
  
 MYWINAPP의 include 섹션에 다음 줄을 삽입 합니다. CPP:  
  
 [!code-cpp[NVC_MFCDocViewSDI#2](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]  
  
 변경 내용을 저장 하 고 단계를 계속 합니다.  
  
##  <a name="vcconnewviewclassa2"></a> 만들고 새 뷰 클래스를 수정 합니다.  
 새 뷰 클래스를 만드는 쉽게 사용 하 여 이루어집니다는 **새 클래스** 클래스 뷰에서 사용할 수 있는 명령입니다. 이 클래스에 대 한 유일한 요구 사항은에서 파생 되며 `CView`합니다. 응용 프로그램에이 새 클래스를 추가 합니다. 프로젝트에 새 클래스를 추가 하는 방법에 대 한 자세한 내용은 참조 하십시오. [클래스 추가](../ide/adding-a-class-visual-cpp.md)합니다.  
  
 프로젝트에 클래스를 추가한 후 일부 뷰 클래스 멤버의 액세스 가능성을 변경 해야 합니다.  
  
 새 보기를 수정 합니다. 액세스 지정자에서 변경 하 여 H `protected` 를 **공용** 생성자 및 소멸자에 대 한 합니다. 이 클래스를를 만들고 동적으로 소멸 및 표시 되기 전에 뷰 모양을 수정할 수 있습니다.  
  
 변경 내용을 저장 하 고 단계를 계속 합니다.  
  
##  <a name="vcconattachnewviewa3"></a> 만들고 연결 하려면 새 보기  
 를 만들고 새 뷰를 연결 하려면 수정 해야는 `InitInstance` 응용 프로그램 클래스의 함수입니다. 새 뷰 개체를 한 다음 초기화 두 만드는 새 코드를 추가 하는 수정 `m_pOldView` 및 `m_pNewView` 두 개의 기존 뷰 개체입니다.  
  
 새 보기 내에서 만들어지므로 `InitInstance` 함수를 신규 및 기존 뷰를 응용 프로그램의 수명 동안 유지 합니다. 그러나 응용 프로그램은 새 보기를 동적으로 만들 손쉽게 수 없습니다.  
  
 이 코드에 대 한 호출 뒤에 삽입 `ProcessShellCommand`:  
  
 [!code-cpp[NVC_MFCDocViewSDI#3](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]  
  
 변경 내용을 저장 하 고 단계를 계속 합니다.  
  
##  <a name="vcconswitchingfunctiona4"></a> 전환 함수 구현  
 이전 단계에서 생성 하 고 새 뷰 개체를 초기화 하는 코드를 추가 합니다. 스위칭 메서드를 구현 하는 마지막 주요 조각을 `SwitchView`합니다.  
  
 응용 프로그램에 대 한 구현 파일의 끝에 클래스 (MYWINAPP 합니다. CPP) 다음과 같은 메서드 정의 추가 합니다.  
  
 [!code-cpp[NVC_MFCDocViewSDI#4](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]  
  
 변경 내용을 저장 하 고 단계를 계속 합니다.  
  
##  <a name="vcconswitchingtheviewa5"></a> 뷰를 전환에 대 한 지원 추가  
 마지막 단계는 호출 하는 코드를 추가 해야는 `SwitchView` 메서드는 응용 프로그램 보기 사이 전환 해야 할 경우. 여러 가지 방법으로이 작업을 수행할 수 있습니다: 사용자가 선택할 수에 대 한 새 메뉴 항목을 추가 하거나 특정 조건이 충족 될 때 내부적으로 뷰를 전환 합니다.  
  
 새 메뉴 항목 및 명령 처리기 함수를 추가 합니다. 자세한 내용은 참조 [명령 및 컨트롤 알림에 대 한 처리기](../mfc/handlers-for-commands-and-control-notifications.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서/뷰 아키텍처](../mfc/document-view-architecture.md)

