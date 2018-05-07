---
title: 복합 문서 지원, MFC 응용 프로그램 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.compdoc
dev_langs:
- C++
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 361ad662ed0bc0f499b35c102502f86d063b8e5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compound-document-support-mfc-application-wizard"></a>MFC 응용 프로그램 마법사, 복합 문서 지원
MFC 응용 프로그램 마법사의이 페이지에서 응용 프로그램에서 제공 하는 활성 및 복합 문서 지원 수준을 나타냅니다. 응용 프로그램에 복합 문서 및 문서 서식 파일을 지원 하기 위해 문서/뷰 아키텍처를 지원 해야 합니다.  
  
 기본적으로 응용 프로그램에는 복합 문서 지원 되지 않습니다 포함 되어 있습니다. 이 기본값을 수락 하면 응용 프로그램 액티브 문서 또는 복합 파일 지원 되지 않습니다.  
  
 **복합 문서 지원**  
 응용 프로그램 컨테이너 지원, 서버 지원, 또는 둘 다 제공 하는지 여부를 결정 합니다. 이 영역에 대 한 자세한 내용은 다음을 참조 하세요.  
  
-   [컨테이너: 컨테이너 구현](../../mfc/containers-implementing-a-container.md)  
  
-   [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)  
  
|옵션|설명|  
|------------|-----------------|  
|**없음**|개체 연결 및 포함 (OLE) 지원 되지 않음을 나타냅니다. 응용 프로그램 마법사는 기본적으로 ActiveX 지원 하지 않는 응용 프로그램을 만듭니다.|  
|**컨테이너**|연결 및 포함 된 개체가 포함 됩니다.|  
|**미니 서버**|응용 프로그램에서 만들고 복합 문서 개체를 관리할 수를 나타냅니다. 미니 서버를 실행할 수 없는 독립 실행형 주석과 포함된 항목만 지원 합니다.|  
|**전체 서버**|응용 프로그램에서 만들고 복합 문서 개체를 관리할 수를 나타냅니다. 전체 서버가 독립 실행형과 연결 하 고 포함 항목을 모두 지원을 실행할 수 있습니다.|  
|**컨테이너/풀 서버**|컨테이너와 서버 응용 프로그램 일 수를 나타냅니다. 컨테이너는 자체 문서에 포함 또는 연결 된 항목을 통합할 수 있는 응용 프로그램. 서버는 컨테이너 응용 프로그램에서 사용 하기 위해 자동화 항목을 만들 수 있는 응용 프로그램.|  
  
 **추가 옵션**  
 응용 프로그램 액티브 문서를 지원 하는지 여부를 나타냅니다. 참조 [액티브 문서](../../mfc/active-documents.md) 이 기능에 대 한 자세한 내용은 합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**액티브 문서 서버**|응용 프로그램 만들고 액티브 문서를 관리할 수를 나타냅니다. 액티브 문서 서버에 대 한 파일 확장명을 지정 해야이 옵션을 선택 하는 경우는 **파일 확장명** 상자에 [문서 템플릿 문자열](../../mfc/reference/document-template-strings-mfc-application-wizard.md) 마법사의 페이지입니다. 참조 [액티브 문서 서버](../../mfc/active-document-servers.md) 자세한 정보에 대 한 합니다.|  
|**액티브 문서 컨테이너**|응용 프로그램의 프레임에 액티브 문서를 포함할 수를 나타냅니다. 예를 들어 Internet Explorer, Office 문서 또는 Microsoft Word 파일 또는 Excel 스프레드시트와 같은 액티브 문서 포함 될 수 있습니다. 참조 [액티브 문서 포함](../../mfc/active-document-containment.md) 자세한 정보에 대 한 합니다.|  
|**복합 파일에 대 한 지원**|복합 파일 형식을 사용 하 여 컨테이너 응용 프로그램의 문서를 serialize 하지 않습니다. 이 옵션은 메모리에 개체를 포함 하는 전체 파일이 로드 합니다. 개별 개체에 증분 저장 가능 하지 않습니다. 한 개체가 변경 하 고 이후에 저장 하는 경우 모든 개체 파일에 저장 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)

