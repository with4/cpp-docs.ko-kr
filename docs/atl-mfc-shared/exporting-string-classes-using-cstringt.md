---
title: "Exporting String Classes Using CStringT | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringT class, exporting strings"
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exporting String Classes Using CStringT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC 개발자는 파생 된 이전에 `CString` 자신의 문자열 클래스를 특수화할 수 있습니다.  Microsoft Visual C\+\+.net \(MFC 8.0\)에  [CString](../atl-mfc-shared/using-cstring.md) 클래스는 템플릿 클래스에 의해 호출 대체 된  [CStringT](../atl-mfc-shared/reference/cstringt-class.md).  이렇게 여러 가지 장점을 제공 합니다.  
  
-   MFC에서 사용할 수 `CString` ATL에서 사용 되는 클래스를 프로젝트 큰 MFC 정적 라이브러리 또는 DLL에 연결 하지 않고.  
  
-   제공 되는 새로운 `CStringT` 템플릿 클래스를 지정할 수 있습니다 `CString` 문자 성분, 유사한 서식 파일에 STL \(표준 템플릿 라이브러리\)를 지정 하는 템플릿 매개 변수를 사용 하 여 동작 합니다.  
  
-   에서는 내보낼 때 문자열 클래스를 직접 사용 하는 DLL에서 `CStringT`, 컴파일러가 자동으로 내보냅니다는 `CString` 기본 클래스입니다.  이후 `CString` 자체는 템플릿 클래스입니다. 컴파일러 인식 하지 않는 한 사용 되 면 컴파일러에서 인스턴스화될 수는 `CString` DLL에서 가져온.  Visual C\+\+ 6.0에서 프로젝트를 Visual C\+\+.net으로 마이그레이션한 것 경우 링커 기호 오류를 곱하는 정의를 본 적 있습니다 `CString` 의 충돌 때문에 `CString` DLL 및 로컬로 인스턴스화된 버전에서 가져온.  이렇게 하려면 적절 한 방법은 아래에 설명 되어 있습니다.  이 문제에 대 한 자세한 내용은 기술 자료 문서를 참조 하십시오 "CString 파생 가져올 때 링크 오류 클래스" \(Q309801\) 또는 MSDN 라이브러리 CD\-ROM에서 [다음 웹 사이트](다음%20웹%20사이트).  
  
 다음 시나리오는 기호 오류가 여러 번 정의 된 클래스를 생성 하도록 링커에 발생 합니다.  가정 하면 내보내기는 `CString`\-파생 클래스 \(`CMyString`\)에서 MFC 확장 DLL:  
  
 [!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/CPP/exporting-string-classes-using-cstringt_1.cpp)]  
  
 소비자 코드의 혼합을 사용 하 여 `CString` 및 `CMyString`. 이때   MyString.h"않는 포함 및 미리 컴파일된 헤더를 사용 하는 `CString` 없는 `CMyString` 표시 합니다.  
  
 사용 하는 가정은 `CString` 및 `CMyString` 별도 소스 파일에서 Source1.cpp 및 Source2.cpp 클래스.  Source1.cpp를 사용 하면 `CMyString` \# Mystring.h를 포함 합니다.  Source2.cpp를 사용 하면 `CString`, 하지만 하지 않습니다 \# Mystring.h를 포함 합니다.  이 경우 링커에 대 한 문제가 발생할 수도 있습니다 `CStringT` 여러 개 정의 하 고 있습니다.  이 인해 `CString` 모두 가져온 DLL에서 내보내는 중인 `CMyString`, 및 컴파일러를 통해 로컬로 인스턴스화된는 `CStringT` 템플릿.  
  
 이 문제를 해결 하려면 다음과 같이 하십시오.  
  
 내보내기 `CStringA` 및 `CStringW` \(및 필요한 기본 클래스\)에서 MFC90.DLL입니다.  MFC를 포함 하는 프로젝트를 내보내는 MFC DLL 항상 사용 `CStringA` 및 `CStringW`, 이전 MFC 구현에 따라.  
  
 다음 사용 하 여 내보낼 수 있는 파생된 클래스를 만들는 `CStringT` 서식으로 `CStringT_Exported` 아래 예입니다:  
  
 [!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/CPP/exporting-string-classes-using-cstringt_2.cpp)]  
  
 Afxstr.h에서 이전 대체 `CString`, `CStringA`, 및 `CStringW` 같이 형식 정의:  
  
 [!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/CPP/exporting-string-classes-using-cstringt_3.cpp)]  
  
 몇 가지 주의 사항이 있습니다.  
  
-   내보내는 해야 `CStringT` 자체는 특수 내보낼 프로젝트를 ATL 전용 포함 시키는 것이 `CStringT` 클래스입니다.  
  
-   내보낼 수 있는 사용 하 여 파생 클래스에서 `CStringT` 다시 구현 하는 것을 최소화할 수 `CStringT` 기능.  추가 코드 생성자에 전달 하는 제한 된 수의 `CStringT` 기본 클래스입니다.  
  
-   `CString` `CStringA`, 및 `CStringW` 만 표시 합니다. `__declspec(dllexport/dllimport)` DLL을 MFC로 작성 하는 경우 공유 합니다.  MFC 정적 라이브러리에 연결 하는 경우에 이러한 클래스 내보낼 때 표시 해야 없습니다. 그렇지 않으면 내부 사용 `CString`, `CStringA`, 및 `CStringW` 내부 사용자 Dll 표시 `CString` 으로.  
  
## 관련 항목  
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)  
  
## 참고 항목  
 [Using CStringT](../atl-mfc-shared/using-cstringt.md)   
 [Using CString](../atl-mfc-shared/using-cstring.md)