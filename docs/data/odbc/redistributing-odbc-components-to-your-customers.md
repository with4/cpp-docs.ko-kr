---
title: 고객에 게 ODBC 구성 요소 재배포 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e0427228b8fb3e852cf1d9ee66a10c9290b860b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-odbc-components-to-your-customers"></a>고객에게 ODBC 구성 요소 재배포
응용 프로그램에 ODBC 관리자 프로그램의 기능을 통합 하는 경우도 배포 해야 사용자에 게 이러한 프로그램을 실행 하는 파일입니다. 이 ODBC 파일의 Visual c + + CD-ROM \OS\System 디렉터리에 있어야 합니다. Redistrb.wri 파일과 동일한 디렉터리에 사용권 계약에는 재배포할 수 있는 ODBC 파일 목록이 포함 되어 있습니다.  
  
 제공 하려는 모든 ODBC 드라이버에 대 한 설명서를 참조 하십시오. 제공 하는 Dll 및 기타 파일을 결정 해야 합니다. 또한 읽어야 [고객에 게 ODBC 구성 요소 재배포](../../data/odbc/redistributing-odbc-components-to-your-customers.md)는 ODBC 구성 요소를 재배포 하는 방법에 설명 합니다.  
  
 또한 대부분의 경우에 다른 파일을 하나 포함 해야 합니다. Odbccr32.dll ODBC 커서 라이브러리입니다. 이 라이브러리는 수준 1 드라이버의 앞 이나 뒤로 스크롤 기능을 제공 합니다. 또한 스냅숏 지원 기능을 제공 합니다. ODBC 커서 라이브러리에 대 한 자세한 내용은 참조 [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)합니다.  
  
 다음 항목에서는 ODBC 데이터베이스 클래스 사용에 대 한 자세한 정보가 표시 됩니다.  
  
-   [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
-   [ODBC: ODBC 데이터 소스 구성](../../data/odbc/odbc-configuring-an-odbc-data-source.md)  
  
-   [ODBC: ODBC API 함수 직접 호출](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)  
  
## <a name="see-also"></a>참고 항목  
 [ODBC 기초](../../data/odbc/odbc-basics.md)   
 [ODBC 관리자](../../data/odbc/odbc-administrator.md)