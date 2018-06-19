---
title: 'ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤 프로그래밍 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- Confirm Classes dialog box
- wrapper classes [MFC], ActiveX controls
- ActiveX control containers [MFC], wrapper classes
- ActiveX controls [MFC], accessing
- MFC ActiveX controls [MFC], accessing in containers
- header files [MFC], for ActiveX control wrapper class
- wrapper classes [MFC], using
- ActiveX controls [MFC], wrapper classes
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bae926cfc7e83edeef9ee68c7ce7118c55009a08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355043"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤 프로그래밍
이 문서에서는 노출 된에 액세스 하기 위한 프로세스를 설명 [메서드](../mfc/mfc-activex-controls-methods.md) 및 [속성](../mfc/mfc-activex-controls-properties.md) ActiveX 컨트롤을 포함 합니다. 기본적으로, 다음이 단계를 수행 합니다.  
  
1.  [ActiveX 컨테이너 프로젝트에 ActiveX 컨트롤 삽입](../mfc/inserting-a-control-into-a-control-container-application.md) 갤러리를 사용 하 여 합니다.  
  
2.  [멤버 변수 정의](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (또는 다른 형식의 액세스) ActiveX와 같은 형식의 래퍼 클래스를 제어 합니다.  
  
3.  [ActiveX 컨트롤을 프로그래밍](#_core_programming_the_activex_control) 래퍼 클래스의 멤버 함수를 사용 하 여 미리 정의 되어 있습니다.  
  
 이 설명에서는 ActiveX 컨트롤을 지 원하는와 대화 상자 기반 프로젝트 (명명 된 컨테이너)를 만들었습니다을 가정 합니다. Circ 샘플 제어 Circ, 결과 프로젝트에 추가 됩니다.  
  
 Circ 컨트롤 (1 단계) 프로젝트에 삽입 되 면 되 면 응용 프로그램의 주 대화 상자에 Circ 컨트롤의 인스턴스를 삽입 합니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>Circ 컨트롤 대화 서식 파일을 추가 하려면  
  
1.  ActiveX 컨트롤 컨테이너 프로젝트를 로드 합니다. 이 예제에서는 사용 된 `Container` 프로젝트.  
  
2.  리소스 보기 탭을 클릭 합니다.  
  
3.  열기는 **대화** 폴더입니다.  
  
4.  기본 대화 상자 템플릿을 두 번 클릭 합니다. 이 예제에서는 **IDD_CONTAINER_DIALOG**합니다.  
  
5.  도구 상자에서 Circ 컨트롤 아이콘을 클릭 합니다.  
  
6.  Circ 컨트롤을 삽입 하는 대화 상자 내에서 한 지점을 클릭 합니다.  
  
7.  **파일** 메뉴 선택 **모두 저장** 대화 상자 템플릿에 모든 수정 내용을 저장 하려면.  
  
## <a name="modifications-to-the-project"></a>프로젝트에 수정  
 Circ 컨트롤에 액세스 하는 컨테이너 응용 프로그램을 사용 하려면 Visual c + + 자동으로 추가 하는 래퍼 클래스 (`CCirc`) 구현 파일 (합니다. CPP) 컨테이너 프로젝트 및 래퍼 클래스 헤더 (합니다. H) 파일 대화 상자 헤더 파일:  
  
 [!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]  
  
##  <a name="_core_the_wrapper_class_header_28h29_file"></a> 래퍼 클래스 헤더 (합니다. H)  
 가져올 속성을 설정 (및 메서드를 호출) Circ 컨트롤에 대 한는 `CCirc` 래퍼 클래스에 노출 된 모든 메서드 및 속성의 선언을 제공 합니다. 예제에서는 이러한 선언에에서 있습니다. 가변 원형 8. 다음 예제는 클래스의 부분 `CCirc` ActiveX 컨트롤의 노출 된 인터페이스를 정의 하는:  
  
 [!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]  
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]  
  
 이러한 함수에서 다른 응용 프로그램의 절차 일반 c + + 구문을 사용 하 여 호출할 수 있습니다. 컨트롤의 메서드 및 속성에 액세스 하도록 설정 하는이 멤버 함수를 사용 하 여에 대 한 자세한 내용은 섹션을 참조 하십시오. [ActiveX 컨트롤 프로그래밍](#_core_programming_the_activex_control)합니다.  
  
##  <a name="_core_member_variable_modifications_to_the_project"></a> 프로젝트에 멤버 변수를 수정  
 ActiveX 컨트롤 프로젝트에 추가 되 고 대화 상자 컨테이너에 포함 된, 되 면 프로젝트의 다른 부분에서 액세스할 수 있습니다. 컨트롤에 액세스 하는 가장 쉬운 방법은 [멤버 변수를 만들고](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) 대화 상자 클래스의 `CContainerDlg` (2 단계), 즉 Visual c + + 프로젝트에 추가 하는 래퍼 클래스와 같은 유형의 합니다. 다음 멤버 변수를 사용 하 여 언제 든 지 포함 된 컨트롤에 액세스 합니다.  
  
 경우는 **멤버 변수 추가** 추가 하는 대화 상자는 `m_circctl` 멤버 프로젝트에 변수를 다음 줄에 추가 하는 헤더 파일 (합니다. H)는 `CContainerDlg` 클래스:  
  
 [!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]  
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]  
  
 에 대 한 호출 또한 **DDX_Control** 자동으로 추가 되 고 `CContainerDlg`의 구현의 `DoDataExchange`:  
  
 [!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]  
  
##  <a name="_core_programming_the_activex_control"></a> ActiveX 컨트롤 프로그래밍  
 이 시점에서 대화 상자 템플릿을에 ActiveX 컨트롤 삽입 서 멤버 변수 용으로 만들어진 했습니다. 이제 포함된 된 컨트롤의 메서드와 속성에 액세스 하려면 일반적인 c + + 구문을 사용할 수 있습니다.  
  
 언급 했 듯이 (에서 [의 래퍼 클래스 헤더 (합니다. H)](#_core_the_wrapper_class_header_28h29_file)), 헤더 파일 (합니다. H)에 `CCirc` 이 case 가변 원형에서 래퍼 클래스 H, 가져오고 모든 노출 된 속성 값을 설정 하는 데 사용할 수 있는 멤버 함수 목록이 포함 되어 있습니다. 멤버 함수 노출 된 메서드를 사용할 수 있습니다.  
  
 에 컨트롤의 속성을 수정할 수 있는 공통 위치는 `OnInitDialog` 주 대화 상자 클래스의 멤버 함수입니다. 이 함수는 하기 바로 전에 호출 대화 상자가 표시 되 고 컨트롤은 컨트롤을 포함 하 여 해당 콘텐츠를 초기화 하는 데 사용 됩니다.  
  
 다음 코드 예제에서는 `m_circctl` 포함된 Circ 컨트롤의 캡션 및 CircleShape 속성을 수정 하는 멤버 변수:  
  
 [!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)

