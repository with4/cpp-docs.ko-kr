---
title: 문서 템플릿 문자열 MFC 클래스 추가 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.class.mfc.simple.doctemp
dev_langs:
- C++
helpviewer_keywords:
- MFC Add Class Wizard, document control strings
ms.assetid: 14e1c834-5e79-4dbd-811f-ec8f0a9cdcb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81b14e0c397ac9179142627bca04b647c1db96db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="document-template-strings-mfc-add-class-wizard"></a>MFC 클래스 추가 마법사, 문서 템플릿 문자열
마법사의이 페이지는 다음 조건을 만족 하는 클래스에만 사용할 수 있습니다.  
  
-   MFC 프로젝트의 문서/뷰 아키텍처를 지원합니다.  
  
-   새 클래스의 기본 클래스는 [CFormView](../../mfc/reference/cformview-class.md)합니다.  
  
-   확인란 **생성 DocTemplate 리소스** 에 확인 표시가 **이름** 의 섹션은 [MFC 클래스 마법사](../../mfc/reference/mfc-add-class-wizard.md)합니다.  
  
 마법사 폼 뷰 디자인, 관리 및 지역화에 도움이 되도록 다음 값에 대 한 기본값을 제공 합니다. 표시 되 고 폼의 사용자가 사용 되는 대부분의 문서 템플릿 문자열 되므로로 지역화 됩니다는 **리소스 언어** 에 표시 된는 [응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) MFC 응용 프로그램 마법사 페이지 프로젝트를 만들 때.  
  
> [!NOTE]
>  마법사에서 파생 된 클래스에 대 한 자동 인쇄 지원을 제공 하지 않습니다 `CFormView`합니다.  
  
 참조 [문서 템플릿 및 문서/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md) 자세한 정보에 대 한 합니다.  
  
## <a name="nonlocalized-strings"></a>지역화 되지 않은 문자열  
 사용자 문서를 만드는 응용 프로그램에 적용 됩니다. 사용자 수 더 열고 저장할 문서 쉽게 문서 형식에 있는 경우 파일 확장명과 파일 유형 id입니다. 사용자가 아니라 시스템에서 사용 되므로 이러한 항목 지역화 되지 않은 합니다.  
  
 **파일 확장명**  
 이 forms 응용 프로그램에 대 한 문서 형식과 연결 된 파일 확장명을 설정 합니다. 클래스 이름에 따라 파일 확장명 기본값입니다. 예를 들어 새 MFC 클래스 이름이 **CWidget**, 기본적으로 파일 확장명은. wid. 파일 확장명은 파일 필터에 사용 되 고 **열려** 및 **다른 이름으로 저장** 대화 상자.  
  
 사용 하는 변경 내용이 반영 파일 확장명을 바꾸면는 **필터 이름을** 상자입니다.  
  
> [!NOTE]
>  기본 파일 확장명을 바꾸면 마침표를 포함 하지 마십시오.  
  
 **파일 유형 ID**  
 시스템 레지스트리에 문서 유형에 대 한 레이블을 설정합니다.  
  
## <a name="localized-strings"></a>지역화 된 문자열  
 양식과 읽고 문자열은 지역화 되므로 응용 프로그램의 사용자가 사용 하는 문서와 연결 된 문자열을 생성 합니다.  
  
 **문서 형식 이름**  
 응용 프로그램의 문서 수 그룹화 문서의 유형을 식별 합니다. 기본적으로 클래스의 이름에 기반 합니다. 예를 들어 새 MFC 클래스 이름이 **CWidget**, 기본적으로 문서 형식 이름은 위젯입니다. 기본값을 변경 해도이 대화 상자에서 다른 옵션은 변경 되지 않습니다.  
  
 **필터 이름**  
 사용자가 지정된 된 파일 형식 파일을 찾으려면 나타낼 수 있는 이름을 설정 합니다. 이 옵션은 사용할 수는 **파일 형식** 및 **파일 형식** windows 표준 옵션 **열려** 및 **다른 이름으로 저장** 대화 상자. 기본적으로 이름이 프로젝트 이름에 따라와 파일을 확장 하 여 뒤에 표시 된 **파일 확장명**합니다. 예를 들어 프로젝트 이름이 위젯, 및 파일 확장명은.wid는 **필터 이름을** 위젯 파일 (*.wid)는 기본적으로 합니다.  
  
 **파일의 새 짧은 이름**  
 표준 Windows에 나타나는 이름을 설정 `New` 대화 상자에서 프로젝트에 있는 경우 문서 서식 파일을 여러 개 있습니다. 응용 프로그램이 [자동화 서버](../../mfc/automation-servers.md), 자동화 개체의 짧은 이름으로이 이름이 사용 됩니다. 기본적으로이 이름은 클래스 이름에 기반 합니다.  
  
 **파일 형식에 대 한 긴 이름**  
 시스템 레지스트리에 파일 형식 이름을 설정합니다. 자동화 서버 응용 프로그램을 사용 하는 경우이 이름은 자동화 개체의 긴 이름으로 사용 됩니다. 기본적으로이 이름은 클래스 이름에 기반 합니다. 문서입니다. 예를 들어, 클래스 이름은 **CWidget**, **파일 형식에 긴 이름** 위젯 문서입니다.  
  
 **문서 클래스**  
 프로젝트의 문서 클래스를 나타냅니다. 기본적으로이 클래스는 기본 응용 프로그램의 문서 클래스에 나열 된는 [생성 된 클래스 검토](../../mfc/reference/generated-classes-mfc-application-wizard.md) MFC 응용 프로그램 마법사의 페이지입니다. 프로젝트의 다른 문서 클래스를 추가 하면 목록에서 다른 문서 클래스를 선택할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 클래스 추가 마법사](../../mfc/reference/mfc-add-class-wizard.md)   
 [MFC 클래스](../../mfc/reference/adding-an-mfc-class.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)
