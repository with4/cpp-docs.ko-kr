---
title: 클래스 추가(Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.classes.adding
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14e16d8b5c15939adb792a96a828bafd07ba4041
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333286"
---
# <a name="adding-a-class-visual-c"></a>클래스 추가(Visual C++)
Visual C++ 프로젝트에서 클래스를 추가하려면 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고, **추가**를 클릭한 다음, **클래스**를 클릭합니다. 그러면 [클래스 추가 대화 상자](../ide/add-class-dialog-box.md) 대화 상자가 열립니다.  
  
 클래스를 추가할 때 MFC 또는 ATL에 이미 존재하는 클래스와 다른 이름을 지정해야 합니다. 라이브러리에 이미 있는 이름을 지정하면 IDE에는 오류 메시지가 표시됩니다.  
  
 프로젝트 명명 규칙에서 기존 이름을 사용해야 하는 경우 C++가 대/소문자를 구분하기 때문에 이름 중 하나 이상의 대/소문자를 변경할 수 있습니다. 예를 들어 클래스를 `CDocument`로 명명할 수 없지만 이름을 `cdocument`로 지정할 수 있습니다.  
  
## <a name="what-kind-of-class-do-you-want-to-add"></a>어떤 종류의 클래스를 추가하시겠습니까?  
 **클래스 추가** 대화 상자의 왼쪽 창에서 **Visual C++** 노드를 확장하면 설치된 템플릿이 여러 개로 그룹화되어 표시됩니다. 그룹에는 **CLR**, **ATL**, **MFC** 및 **C++** 이 포함됩니다. 그룹을 선택하면 해당 그룹에서 사용 가능한 템플릿 목록이 가운데 창에 표시됩니다. 각 템플릿에는 클래스에 필요한 파일 및 소스 코드가 포함되어 있습니다.  
  
 새 클래스를 생성하려면 중간 창에서 템플릿을 선택하고, **이름** 상자에 클래스의 이름을 입력하고, **추가**를 클릭합니다. 그러면 클래스의 옵션을 지정할 수 있도록 **클래스 추가 마법사**가 열립니다.  
  
-   MFC 클래스를 만드는 방법에 대한 자세한 내용은 [MFC 클래스](../mfc/reference/adding-an-mfc-class.md)를 참조하세요.  
  
-   ATL 클래스를 만드는 방법에 대한 자세한 내용은 [ATL 단순 개체](../atl/reference/adding-an-atl-simple-object.md)를 참조하세요.  
  
> [!NOTE]
>  템플릿 **MFC에 ATL 지원 추가**에서는 클래스를 만들지 않지만 대신 ATL을 사용하도록 프로젝트를 구성합니다. 자세한 내용은 [MFC 프로젝트의 ATL 지원](../mfc/reference/adding-atl-support-to-your-mfc-project.md)을 참조하세요.  
  
 C++ 클래스가 MFC, ATL 또는 CLR을 사용하지 않도록 하려면 설치된 템플릿의 **C++** 그룹에서 **C++ 클래스** 템플릿을 사용합니다. 자세한 내용은 [제네릭 C++ 클래스 추가](../ide/adding-a-generic-cpp-class.md)를 참조하세요.  
  
 두 종류의 양식 기반 C++클래스가 지원됩니다. 첫 번째 [CFormView 클래스](../mfc/reference/cformview-class.md)는 MFC 클래스를 만듭니다. 두 번째는 Windows Forms CLR 클래스를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [폼 기반 MFC 응용 프로그램 만들기](../mfc/reference/creating-a-forms-based-mfc-application.md)   
 [클래스 추가 대화 상자](../ide/add-class-dialog-box.md)   
 [응용 프로그램 마법사를 사용하여 데스크톱 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [코드 마법사에서 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)