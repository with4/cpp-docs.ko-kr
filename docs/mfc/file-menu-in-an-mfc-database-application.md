---
title: "MFC 데이터베이스 응용 프로그램에서 파일 메뉴 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- File menu
- database applications [MFC], File menu commands
ms.assetid: 92dafb75-c1b3-4860-80a0-87a83bfc36f2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51f630f5a3fe1ee5833ac2796ff2acb1841af4c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="file-menu-in-an-mfc-database-application"></a>MFC 데이터베이스 응용 프로그램의 파일 메뉴
어떻게 해야 하면 해석 열기, 닫기, 저장 및 다른 이름으로 저장 명령을 파일 메뉴에서 MFC 데이터베이스 응용 프로그램을 만들고 serialization을 사용 하지 않는 경우 다음은 몇 가지 제안 사항이이 질문에 대 한 스타일 지정 지침 없음 상태인:  
  
-   파일 메뉴 열기 명령을 완전히 제거 합니다.  
  
-   "Open database"로 열기 명령을 해석 하 고 사용자에 게 응용 프로그램에서 인식 하는 데이터 원본의 목록을 표시 합니다.  
  
-   다른 이름으로 열기"프로필." 열기 명령을 해석합니다 보존 열기 his를 포함 하는 사용자의 기본 설정 등의 "사용자 프로필" 정보를 포함 하는 직렬화 된 문서를 저장할 파일을 사용 하지만 serialize 된 파일을 여 (필요한 경우 암호 제외)의 로그인 ID와 데이터 원본 자신이 가장 최근에 사용한 합니다.  
  
 MFC 응용 프로그램 마법사 없는 문서와 관련 된 파일 메뉴 명령을 사용 하 여 응용 프로그램 만들기를 지원 합니다. 선택는 **데이터베이스 파일을 지원 하지 않는 뷰** 옵션에 **데이터베이스 지원** 페이지.  
  
 대부분의 하나 이상의 명령 처리기를 재정의 해야 하는 특수 한 방법으로 파일 메뉴 명령을 해석 하 여 `CWinApp`-클래스를 파생 합니다. 예를 들어, 완전히 재정의 하는 경우 `OnFileOpen` (구현 하는 `ID_FILE_OPEN` 명령)을 의미 "열려 있는 데이터베이스:"  
  
-   기본 클래스 버전을 호출 하지 마세요 `OnFileOpen`이므로 명령 프레임 워크의 기본 구현을 완전히 대체 하 합니다.  
  
-   데이터 원본을 나열 하는 대화 상자를 표시 하려면 처리기를 대신 사용 합니다. 호출 하 여 이러한 대화 상자를 표시할 수 있습니다 `CDatabase::OpenEx` 또는 `CDatabase::Open` 매개 변수와 함께 **NULL**합니다. 사용자의 컴퓨터에 모든 사용 가능한 데이터 소스를 표시 하는 ODBC 대화 상자가 열립니다.  
  
-   일반적으로 데이터베이스 응용 프로그램 전체 문서를 저장 하지 않습니다, 해도 좋을 것 저장을 제거 하 고 serialize 된 문서를 사용 하 여 프로필 정보를 저장 하지 않는 한 구현으로 저장 합니다. 다른 이름으로 예를 들어 "트랜잭션을 커밋할." 저장 명령을 구현 하는 그렇지 않은 경우 참조 [Technical Note 22](../mfc/tn022-standard-commands-implementation.md) 재정의 이러한 명령에 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Serialization: Serialization과 데이터베이스 입/출력](../mfc/serialization-serialization-vs-database-input-output.md)

