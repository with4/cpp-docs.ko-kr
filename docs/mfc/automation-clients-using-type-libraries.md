---
title: '자동화 클라이언트: 형식 라이브러리를 사용 하 여 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MkTypLib
dev_langs:
- C++
helpviewer_keywords:
- clients, Automation
- dispatch class [MFC]
- Automation clients, type libraries
- type libraries, Automation clients
- ODL (Object Description Language)
- ODL files
- classes [MFC], dispatch
- MkTypLib tool
- .odl files
ms.assetid: d405bc47-118d-4786-b371-920d035b2047
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67fa0f5d164ae325caff576fb41695fc8689fda0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342591"
---
# <a name="automation-clients-using-type-libraries"></a>자동화 클라이언트: 형식 라이브러리 사용
자동화 클라이언트는 클라이언트에서 서버의 개체를 조작 하는 경우 서버 개체의 속성 및 메서드에 대 한 정보가 있어야 합니다. 속성에는 데이터 형식입니다. 메서드 반환 값을 매개 변수를 허용 합니다. 클라이언트에는 서버 개체 유형에 정적 바인딩하기 위해서는 모든 속성 및 메서드의 데이터 형식에 대 한 정보를 필요 합니다.  
  
 이 유형 정보는 알려진 여러 가지 방법으로 만들 수 있습니다. 형식 라이브러리를 만드는 것이 좋습니다.  
  
 에 대 한 내용은 [MkTypLib](http://msdn.microsoft.com/library/windows/desktop/aa366797), Windows SDK를 참조 하십시오.  
  
 Visual c + + 형식 라이브러리 파일을 읽을 수 및 디스패치 클래스에서 파생 된 만들 [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)합니다. 해당 클래스의 개체 속성 및 서버 개체의 복제 작업에 있습니다. 이 개체의 속성 및 작업을 호출 하는 응용 프로그램 및 기능에서 상속 되며, `COleDispatchDriver` 차례로 서버 개체에 라우팅하는 OLE 시스템에 이러한 호출을 라우팅합니다.  
  
 Visual c + + 자동으로 유지 관리이 형식 라이브러리 파일을 프로젝트를 만들 때 자동화를 포함 하는 경우. 각 빌드의 일부로.tlb 파일을 사용 하 여가 빌드됩니다.  
  
### <a name="to-create-a-dispatch-class-from-a-type-library-tlb-file"></a>형식 라이브러리 (.tlb) 파일에서 디스패치 클래스를 만들려면  
  
1.  클래스 뷰 또는 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **추가** 클릭 하 고 **클래스 추가** 바로 가기 메뉴.  
  
2.  에 **클래스 추가** 대화 상자는 **Visual C + MFC** 왼쪽된 창에서 폴더입니다. 선택 된 **TypeLib의 MFC 클래스** 클릭 확인 하 고 오른쪽 창에서 아이콘 **열려**합니다.  
  
3.  에 **Typelib의 클래스 추가 마법사** 대화 상자에서 형식 라이브러리를 선택 합니다는 **사용 가능한 형식 라이브러리** 드롭 다운 목록입니다. **인터페이스** 상자 선택한 형식 라이브러리에 대해 사용할 수 있는 인터페이스에 표시 됩니다.  
  
    > [!NOTE]
    >  둘 이상의 형식 라이브러리에서 인터페이스를 선택할 수 있습니다.  
  
     인터페이스를 선택, 두 번 클릭 하거나 클릭 하 고 **추가** 단추입니다. 이렇게 하면 디스패치 클래스에 대 한 이름에 표시 됩니다는 **생성 된 클래스** 상자입니다. 클래스 이름을 편집할 수는 `Class` 상자입니다.  
  
     **파일** 클래스 선언할 수 있는 파일 상자에 표시 됩니다. (이 파일 이름은 편집할 수 있습니다). 또한 기존 파일이 나 프로젝트 디렉터리가 아닌 다른 디렉터리에 작성 된 헤더 및 구현 정보가 선호 하는 경우 다른 파일을 선택 하려면 찾아보기 단추를 사용할 수 있습니다.  
  
    > [!NOTE]
    >  선택한 인터페이스에 대 한 모든 디스패치 클래스는 여기에서 지정 된 파일에 저장 됩니다. 별도 헤더에 선언에 대 한 인터페이스를 사용 하도록 하려는 경우에 만들려는 각 헤더 파일에 대 한이 마법사를 실행 해야 합니다.  
  
    > [!NOTE]
    >  일부 형식 라이브러리 정보를 사용 하 여 파일에 저장할 수 있습니다. DLL입니다. OCX, 또는. OLB 파일 확장명입니다.  
  
4.  **마침**을 클릭합니다.  
  
     마법사는 다음 지정 된 클래스 및 파일 이름을 사용 하 여 디스패치 클래스에 대 한 코드를 작성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [자동화 클라이언트](../mfc/automation-clients.md)

