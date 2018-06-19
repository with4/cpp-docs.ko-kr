---
title: 형식 라이브러리에서 MFC 클래스 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 349d06d7fecb82af64fbf2d3b2ebe54689b3b292
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355118"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>형식 라이브러리에서 MFC 클래스 추가
이 마법사를 사용 하 여 인터페이스에 사용 가능한 형식 라이브러리에는 MFC 클래스를 만듭니다. 에 MFC 클래스를 추가할 수는 [MFC 응용 프로그램](../../mfc/reference/creating-an-mfc-application.md), [MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md), 또는 [MFC ActiveX 컨트롤](../../mfc/reference/creating-an-mfc-activex-control.md)합니다.  
  
> [!NOTE]
>  형식 라이브러리에서 클래스를 추가할 수 있도록 설정 하는 자동화가 포함 된 MFC 프로젝트를 만들 필요가 없습니다.  
  
 형식 라이브러리와 매개 변수 및 반환 형식 메서드 정의 구성 요소에 의해 노출 되는 인터페이스에 대 한 이진 설명을 포함 합니다. 에 표시할에 대 한 형식 라이브러리를 등록 해야 합니다는 **사용 가능한 형식 라이브러리** Typelib 마법사에서 추가 클래스 목록입니다. 내부 Distributed COM:: 형식 라이브러리 및 언어의에서 "통합"에 대 한 자세한 내용은 MSDN library 참조 하십시오.  
  
### <a name="to-add-an-mfc-class-from-a-type-library"></a>형식 라이브러리에서 MFC 클래스를 추가 하려면  
  
1.  **솔루션 탐색기** 또는 [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), 클래스를 추가 하려면 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴에서 클릭 **추가**, 클릭 하 고 **클래스 추가**합니다.  
  
3.  에 [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자의 템플릿 창에서 클릭 **Typelib의 MFC 클래스**, 클릭 하 고 **열려** 표시 하는 [Typelib 마법사에서 클래스 추가 ](../../mfc/reference/add-class-from-typelib-wizard.md).  
  
 마법사에서 형식 라이브러리의 클래스 두 개 이상 추가할 수 있습니다. 마찬가지로, 단일 마법사 세션에서 둘 이상의 형식 라이브러리에서 클래스를 추가할 수 있습니다.  
  
 마법사에서 파생 하는 MFC 클래스를 만듭니다. [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md), 선택한 형식 라이브러리에서 추가할 각 인터페이스에 대 한 합니다. `COleDispatchDriver` OLE 자동화의 클라이언트 쪽을 구현 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [자동화 클라이언트](../../mfc/automation-clients.md)   
 [자동화 클라이언트: 형식 라이브러리 사용](../../mfc/automation-clients-using-type-libraries.md)

