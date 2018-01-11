---
title: "문서 템플릿 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04950601a74b1ed3e44b236e1d07dcdff997eca6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="document-template-creation"></a>문서 템플릿 만들기
에 대 한 응답에서 새 문서를 만들 때 한 `New` 또는 **열려** 명령을 **파일** 메뉴 문서 서식 파일 문서를 볼 수 있는 새 프레임 창을 만듭니다.  
  
 문서 템플릿 생성자는 어떤 종류의 문서, 창 및 뷰 템플릿을 만들 수 수를 지정 합니다. 이 문서 서식 파일 생성자에 전달할 인수에 의해 결정 됩니다. 다음 코드에서는 생성 한 [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) 샘플 응용 프로그램:  
  
 [!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]  
  
 새 포인터 `CMultiDocTemplate` 개체에 대 한 인수로 [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate)합니다. 에 대 한 인수는 `CMultiDocTemplate` 생성자 문서 종류의 메뉴 및 액셀러레이터를와 연결 된 리소스 ID 등의 사용을 3 개는 [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) 매크로입니다. `RUNTIME_CLASS`반환 된 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 인수로 서 라는 c + + 클래스에 대 한 개체입니다. 세 개의 `CRuntimeClass` 문서 서식 파일 생성자에 전달 된 개체는 문서를 만드는 프로세스 동안 지정된 된 클래스의 새 개체를 만드는 데 필요한 정보를 제공 합니다. 예제에는 만드는 문서 템플릿 만드는 방법을 보여 줍니다. `CScribDoc` 개체와 함께 `CScribView` 연결 개체입니다. 뷰는 표준 MDI 자식 프레임 창으로 묶여 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [문서/뷰 만들기](../mfc/document-view-creation.md)   
 [MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)   
 [새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)

