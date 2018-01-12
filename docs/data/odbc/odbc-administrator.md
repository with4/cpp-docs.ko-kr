---
title: "ODBC 관리자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- installing ODBC
- ODBC data sources [C++], ODBC Administrator
- ODBC drivers [C++], installing
- ODBC [C++], ODBC Administrator
- Administrator in ODBC
- administration ODBC Administrator
- ODBC Administrator [C++]
- drivers [C++], ODBC
ms.assetid: b8652790-3437-4e7d-bc83-6ea6981f008b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a7d60f11457e509ae67da83aa6bc589af1ce43a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-administrator"></a>ODBC 관리자
ODBC 관리자를 등록 하 고 구성는 [데이터 소스](../../data/odbc/data-source-odbc.md) 있습니다 사용할 수 있는 로컬 또는 네트워크를 통해 합니다. ODBC 관리자가 제공 하는 정보를 사용 하 여 사용자가 데이터 원본에 연결 하는 응용 프로그램에서 코드를 만들려면 마법사.  
  
 MFC ODBC 클래스 또는 MFC 데이터 액세스 개체 (DAO) 클래스와 함께 사용할 ODBC 데이터 소스를 설정 하려면 먼저 등록 하며 데이터 원본을 구성 합니다. ODBC 관리자를 사용 하 여 추가 하 고 데이터 원본을 제거 합니다. ODBC 드라이버에 따라 새 데이터 소스를 만들 수 있습니다.  
  
 ODBC 관리자를 설치 하는 동안 설치 됩니다. 선택한 경우 **사용자 지정** 설치에서 ODBC 드라이버를 선택 하지 않은 **데이터베이스 옵션** 대화 상자에서 필요한 파일 설치를 다시 설치 프로그램을 실행 해야 합니다.  
  
 설치 시 설치 하려면 ODBC 드라이버를 선택 합니다. 나중에 Visual c + + 설치 프로그램을 사용 하 여 Visual c + +와 함께 제공 되는 추가 드라이버를 설치할 수 있습니다.  
  
 Visual c + + 제공 되지 않는 ODBC 드라이버를 설치 하려는 경우 해당 드라이버를 포함 하는 설치 프로그램을 실행 해야 합니다.  
  
#### <a name="to-install-odbc-drivers-that-ship-with-visual-c"></a>Visual c + + 제공 ODBC 드라이버를 설치 하려면  
  
1.  Visual c + + 배포 CD에서 설치 프로그램을 실행 합니다.  
  
     여는 설치 프로그램에서 대화 상자를 표시 합니다.  
  
2.  클릭 **다음** 에 도달할 때까지 각 대화 상자에서는 **설치 옵션** 대화 상자. 선택 **사용자 지정**, 클릭 하 고 `Next`합니다.  
  
3.  모든 확인란의 선택을 취소는 **Microsoft Visual c + + 설치** 제외 하 고 대화 상자는 **데이터베이스 옵션** 확인란을 선택한 다음 클릭 **세부 정보** 는 표시할**데이터베이스 옵션** 대화 상자.  
  
4.  지우기는 **Microsoft Data Access Objects** 확인란을 선택 된 **Microsoft ODBC Driver** 확인란을 선택한 다음 클릭 **세부 정보**합니다.  
  
     **Microsoft ODBC Driver** 대화 상자가 나타납니다.  
  
5.  설치 하 고 클릭 하려는 드라이버 선택 **확인** 두 번입니다.  
  
6.  클릭 **다음** 설치를 시작 하려면 나머지 대화 상자에서 합니다. 설치 프로그램에서 설치가 완료 되 면이 알려 줍니다.  
  
 드라이버를 설치 하는 경우에 ODBC 관리자를 사용 하 여 데이터 소스를 구성할 수 있습니다. 제어판의 ODBC 아이콘을 찾을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [데이터 소스(ODBC)](../../data/odbc/data-source-odbc.md)