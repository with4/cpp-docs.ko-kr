---
title: 문서 템플릿 및 문서 뷰 만들기 프로세스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- icons, for multiple document templates
- document templates [MFC], and views
- document/view architecture [MFC], creating document/view
- single document template
- MFC, document templates
- multiple document template
- CDocTemplate class [MFC]
- templates [MFC], document templates
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2d8308e69cf53db4be51f6ce742df41edaa89ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="document-templates-and-the-documentview-creation-process"></a>문서 템플릿 및 문서/뷰 만들기 프로세스
두 문서 서식 파일 클래스를 사용 하는 프레임 워크 관련된 뷰 및 프레임 창 항목과 함께 문서를 만들기의 복잡 한 프로세스를 관리 하려면: [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) SDI 응용 프로그램에 대 한 및 [CMultiDocTemplate ](../mfc/reference/cmultidoctemplate-class.md) MDI 응용 프로그램에 대 한 합니다. A `CSingleDocTemplate` 만들고 한 번에 한 종류의 한 문서를 저장할 수 있습니다. A `CMultiDocTemplate` 열려 있는 문서를 다양 한 형식의 목록을 유지 합니다.  
  
 일부 응용 프로그램에는 여러 문서 유형을 지원 합니다. 예를 들어 응용 프로그램 문서 텍스트와 그래픽 문서를 지원할 수 있습니다. 이러한 응용 프로그램에서 파일 메뉴에서 새 명령을 선택 하면 대화 상자에는 가능한 형식의 새 문서를 열려면 목록을 표시 합니다. 각 지원 되는 문서 형식에 대 한 응용 프로그램이 고유한 문서 템플릿 개체를 사용 합니다. 다음 그림에서는 두 문서 형식을 지원 하 고 여러 개의 열린 문서를 표시 하는 MDI 응용 프로그램의 구성을 보여 줍니다.  
  
 ![MDI 응용 프로그램을 2 가지 문서 형식이](../mfc/media/vc387h1.gif "vc387h1")  
두 문서 형식을 사용하는 MDI 응용 프로그램  
  
 문서 서식 파일 생성 및 application 개체에서 유지 관리 됩니다. 주요 작업 중 하나가 수행 하는 동안 응용 프로그램의 `InitInstance` 적절 한 종류의 하나 이상의 문서 템플릿이 생성 하는 기능입니다. 이 기능에 설명 되어 [문서 서식 파일 만들기](../mfc/document-template-creation.md)합니다. 응용 프로그램 개체는 해당 템플릿 목록에 각 문서 서식 파일에 대 한 포인터를 저장 하 고 문서 서식 파일을 추가 하기 위한 인터페이스를 제공 합니다.  
  
 두 개 이상의 문서 형식을 지원 해야 하는 경우에 추가로 호출을 추가 해야 [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) 각 문서 유형에 대 한 합니다.  
  
 아이콘은 문서 서식 파일의 응용 프로그램의 목록에서 해당 위치에 따라 각 문서 서식 파일에 등록 됩니다. 문서 서식 파일의 순서를 호출 하 여 추가 된 순서에 따라 결정 됩니다 `AddDocTemplate`합니다. MFC 응용 프로그램에서 첫 번째 아이콘 리소스는 응용 프로그램 아이콘, 다음 아이콘 리소스는 첫 번째 문서 아이콘을 가정 합니다.  
  
 예를 들어 문서 템플릿은 응용 프로그램에 대 한 3의 3입니다. 인덱스 3에 응용 프로그램의 아이콘 리소스 있으면 문서 서식 파일에 대 한 해당 아이콘이 사용 됩니다. 그렇지 않은 경우 인덱스 0에 있는 아이콘은 기본적으로 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [일반 MFC 항목](../mfc/general-mfc-topics.md)   
 [문서 서식 파일 만들기](../mfc/document-template-creation.md)   
 [문서/뷰 만들기](../mfc/document-view-creation.md)   
 [MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)   
 [새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)

