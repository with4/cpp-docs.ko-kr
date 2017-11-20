---
title: "CStringT를 사용 하 여 String 클래스 내보내기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0f3d72b72280ecc841cc349f20c68f90a6cbd227
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="exporting-string-classes-using-cstringt"></a>CStringT를 사용 하 여 String 클래스 내보내기
이전에 MFC 개발자는에서 파생 된 `CString` 를 자신의 문자열 클래스 특수화입니다. Microsoft Visual c + +.net (MFC 8.0)는 [CString](../atl-mfc-shared/using-cstring.md) 클래스 호출 하는 템플릿 클래스에 의해 대체 된 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)합니다. 이 몇 가지 이점을 제공 합니다.  
  
-   MFC를 허용 `CString` 큰 MFC 정적 라이브러리 또는 DLL에 연결 하지 않고 프로젝트 클래스 ATL에서 사용할 수 있습니다.  
  
-   새 `CStringT` 템플릿 클래스를 사용자 지정할 수 있습니다 `CString` c + + 표준 라이브러리의 템플릿에 유사한 문자 특성을 지정 하는 템플릿 매개 변수를 사용 하 여 동작 합니다.  
  
-   사용 하 여 DLL에서 고유한 문자열 클래스를 내보낼 때 `CStringT`, 컴파일러에서 자동으로 내보내는 `CString` 기본 클래스입니다. 이후 `CString` 템플릿 클래스는 그 자체가 컴파일러에서 인식 하지 않는 한 컴파일러를 사용 하 여 인스턴스화할 수 있습니다 하 `CString` DLL에서 가져왔습니다. 프로젝트를 Visual c + + 6.0에서에서 Visual c + +.net를 마이그레이션한 경우 수에 대해 알아보았습니다는 곱하기 정의 대 한 링커 기호 오류 `CString` 의 충돌 때문에 `CString` 는 DLL과 로컬로 인스턴스화된 버전에서 가져온입니다. 이 작업을 수행 하는 올바른 방법은 다음과 같습니다. 이 문제에 대 한 자세한 내용은 기술 자료 문서를 참조 하십시오. "링크 오류 CString 파생을 가져올 때 클래스" (Q309801)에서 [http://support.microsoft.com/default.aspx](http://support.microsoft.com/default.aspx)합니다.  
  
 다음 시나리오는 여러 번 정의 된 클래스에 대 한 기호 오류를 생성 하도록 링커에 발생 합니다. 내보내는 경우를 가정는 `CString`-파생 클래스 (`CMyString`)는 MFC 확장 DLL에서에서:  
  
 [!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]  
  
 소비자 코드의 혼합을 사용 하 여 `CString` 및 `CMyString`합니다. "MyString.h" 미리 컴파일된 헤더와의 몇 가지 사용법에 포함 되지 않은 `CString` 없는 `CMyString` 표시 합니다.  
  
 사용 하 여는 `CString` 및 `CMyString` Source1.cpp 및 Source2.cpp 별도 소스 파일의 클래스에에서 있습니다. Source1.cpp를 사용 하 여 `CMyString` 및 #include MyString.h 합니다. Source2.cpp를 사용 하 여 `CString`, 하는데 일치 하지 않으면 #include MyString.h 합니다. 이 경우 링커는 불평 `CStringT` 되 고 여러 번 정의 되었습니다. 이 문제의 원인은 `CString` 둘 다를 내보내는 DLL에서 가져온 되 고 `CMyString`를 통해 컴파일러에서 로컬로 인스턴스화할는 `CStringT` 서식 파일입니다.  
  
 이 문제를 해결 하려면 다음을 수행 합니다.  
  
 내보내기 `CStringA` 및 `CStringW` (및 필요한 기본 클래스)에서 MFC90 합니다. DLL입니다. MFC를 포함 하는 프로젝트는 내보낸 MFC DLL을 사용 항상 `CStringA` 및 `CStringW`와 같이, 이전 MFC 구현 합니다.  
  
 그런 다음 사용 하 여 내보낼 수 있는 파생된 클래스를 만듭니다는 `CStringT` 템플릿을으로 `CStringT_Exported` 예를 들어 미만인:  
  
 [!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]  
  
 AfxStr.h, 대체 이전 `CString`, `CStringA`, 및 `CStringW` 다음과 같이 형식 정의:  
  
 [!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]  
  
 몇 가지 주의 사항이 있습니다.  
  
-   내보내면 안 `CStringT` 자체는 특수화 된 내보낼 ATL 전용 프로젝트를 일으키므로 `CStringT` 클래스입니다.  
  
-   프로그램 내보낼 수를 사용 하 여 파생 클래스에서 `CStringT` 를 다시 구현 하지 최소화 `CStringT` 기능입니다. 추가 코드는 생성자에 전달 하는 제한 된 `CStringT` 기본 클래스입니다.  
  
-   `CString``CStringA`, 및 `CStringW` 표시할 수만 `__declspec(dllexport/dllimport)` DLL을 공유 하는 MFC로 작성 하는 경우. 경우, MFC 정적 라이브러리에 링크 하지로 표시 해야 이러한 클래스; 내보낼 처럼 그렇지 않으면, 내부 사용 `CString`, `CStringA`, 및 `CStringW` 내 사용자 Dll로 표시 됩니다 `CString` 도 내보낼 처럼 합니다.  
  
## <a name="related-topics"></a>관련 항목  
 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)  
  
## <a name="see-also"></a>참고 항목  
 [CStringT를 사용 하 여](../atl-mfc-shared/using-cstringt.md)   
 [CString 사용](../atl-mfc-shared/using-cstring.md)

