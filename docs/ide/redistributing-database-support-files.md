---
title: "데이터베이스 지원 파일 재배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- redistributing database support files
- database support files [C++], redistributing
ms.assetid: d80cffe0-177c-4515-9de7-fbf0517eb8d6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7517222b1dc2e61f45c23a9fc91709672f304768
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="redistributing-database-support-files"></a>데이터베이스 지원 파일 재배포
에 대 한 개체 DAO (Data Access) 및 Microsoft Data Access SDK에 포함 된 데이터베이스 기술을 대 한 지원 파일을 재배포할 수 있습니다.  
  
## <a name="installing-dao-support-files"></a>DAO 지원 파일 설치  
 DAO의 최신 버전을 가져오려면 참조 [문서 239114: Microsoft Jet 4.0 데이터베이스 엔진에 대 한 최신 서비스 팩을 구하는 방법](http://go.microsoft.com/fwlink/p/?linkid=198014) Microsoft 지원 웹 사이트에 있습니다.  
  
## <a name="installing-microsoft-data-access-sdk-support-files"></a>Microsoft Data Access SDK 지원 파일 설치  
 Mdac_typ.exe를 사용 하 여 ODBC, OLE DB, ADO ActiveX Data Objects (), 및 원격 데이터 서비스 (RDS)에 대 한 지원을 설치 해야 합니다. Mdac_typ.exe는 Visual Studio 설치 미디어의 \WCU\MDAC28\ 폴더에 있습니다. Mdac_typ.exe를 다운로드할 수도 있습니다는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/p/?linkid=198015) 웹 사이트입니다.  
  
 자세한 내용은는 [MSDN](http://go.microsoft.com/fwlink/p/?linkid=198016) 웹 사이트에서 "MDAC 2.8 SP1 재배포"에 대 한 검색입니다. Visual Studio 설치 프로젝트 응용 프로그램 배포를 사용 하는 경우 참조 [배포 및 종속성](http://msdn.microsoft.com/en-us/49e9b84d-bd6a-4388-b9ac-46ea79cf0733)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 파일 재배포](../ide/redistributing-visual-cpp-files.md)