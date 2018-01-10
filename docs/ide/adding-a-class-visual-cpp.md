---
title: "추가 클래스 (Visual c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.classes.adding
dev_langs: C++
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d767bd0afa85bc417cd33ce305ffe0061104bf64
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-class-visual-c"></a>클래스 추가(Visual C++)
Visual c + + 프로젝트의 클래스에 추가 하려면 **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 하 여 **추가**, 클릭 하 고 **클래스**합니다. 열립니다는 [클래스 추가 대화 상자](../ide/add-class-dialog-box.md) 대화 상자.  
  
 MFC 또는 ATL.에 이미 존재 하는 클래스에서 다른 이름을 지정 해야 클래스를 추가 하는 경우 라이브러리에 이미 존재 하는 이름을 지정 하면 지정된 된 이름을 이미 예약 되어 있음을 나타내는 메시지는 Visual c + +에 표시 됩니다.  
  
 프로젝트 명명 규칙에 기존 이름을 사용 해야 하는 경우 다음 변경할 수 있습니다만 이름에 하나 이상 문자의 대/소문자 Visual c + +는 대/소문자 구분 합니다. 예를 들어, 클래스 이름 있지만 `CDocument`, 이름을 지정할 수 있습니다 `cdocument`합니다.  
  
## <a name="what-kind-of-class-do-you-want-to-add"></a>어떤 종류의 클래스를 추가 하 시겠습니까?  
 에 **클래스 추가** 확장 대화 상자는 **Visual c + +** 설치 된 템플릿 여러 그룹화 표시 되는 왼쪽된 창에서 노드. 그룹에 포함 **CLR**, **ATL**, **MFC**, 및 **c + +**합니다. 그룹을 선택 하면 해당 그룹의 사용 가능한 템플릿 목록이 가운데 창에 표시 됩니다. 파일 및 소스 코드는 클래스에 필요한 각 서식 파일에 포함 되어 있습니다.  
  
 새 클래스를 생성 하려면 중간 창에서 템플릿을 선택, 클래스에 대 한 이름을 입력 된 **이름** 고 클릭 **추가**합니다. 열립니다는 **클래스 추가 마법사** 클래스에 대 한 옵션을 지정할 수 있도록 합니다.  
  
-   MFC 클래스를 만드는 방법에 대 한 자세한 내용은 참조 [MFC 클래스](../mfc/reference/adding-an-mfc-class.md)합니다.  
  
-   ATL 클래스를 만드는 방법에 대 한 자세한 내용은 참조 [ATL 단순 개체](../atl/reference/adding-an-atl-simple-object.md)합니다.  
  
> [!NOTE]
>  서식 파일 **MFC에 ATL 지원 추가** 클래스를 만들지 않습니다 하지만 대신 ATL. 사용 하도록 프로젝트를 구성 자세한 내용은 참조 [MFC 프로젝트에 ATL 지원](../mfc/reference/adding-atl-support-to-your-mfc-project.md)합니다.  
  
 MFC, ATL 또는 CLR을 사용 하지 않는 c + + 클래스를 사용는 **c + + 클래스** 에서 서식 파일은 **c + +** 설치 된 템플릿 그룹입니다. 자세한 내용은 참조 [일반 c + + 클래스 추가](../ide/adding-a-generic-cpp-class.md)합니다.  
  
 두 종류의 양식 기반 c + + 클래스는 사용할 수 있는 합니다. 첫 번째 [CFormView 클래스](../mfc/reference/cformview-class.md) 는 MFC 클래스를 만듭니다. 두 번째는 Windows Forms CLR 클래스를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [폼 기반 MFC 응용 프로그램 만들기](../mfc/reference/creating-a-forms-based-mfc-application.md)   
 [클래스 추가 대화 상자](../ide/add-class-dialog-box.md)   
 [응용 프로그램 마법사를 사용 하 여 데스크톱 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)