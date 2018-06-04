---
title: 데이터베이스 지원 파일 재배포 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- redistributing database support files
- database support files [C++], redistributing
ms.assetid: d80cffe0-177c-4515-9de7-fbf0517eb8d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a51697367480569e2d27a4cb67791f5fe4d39a8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323877"
---
# <a name="redistributing-database-support-files"></a>데이터베이스 지원 파일 재배포
DAO(Data Access Objects) 및 Microsoft Data Access SDK의 데이터베이스 기술을 위한 지원 파일을 재배포할 수 있습니다.  
  
## <a name="installing-dao-support-files"></a>DAO 지원 파일 설치  
 최신 버전의 DAO를 받으려면 Microsoft 지원 웹 사이트에서 [문서 239114: Microsoft Jet 4.0 데이터베이스 엔진용 최신 서비스 팩을 받는 방법](http://go.microsoft.com/fwlink/p/?linkid=198014)을 참조하세요.  
  
## <a name="installing-microsoft-data-access-sdk-support-files"></a>Microsoft Data Access SDK 지원 파일 설치  
 Mdac_typ.exe를 사용하여 ODBC, OLE DB, ADO(ActiveX Data Objects) 및 RDS(Remote Data Services)에 대한 지원을 설치합니다. Mdac_typ.exe는 Visual Studio 설치 미디어의 \WCU\MDAC28\ 폴더에 있습니다. [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/p/?linkid=198015) 웹 사이트에서 Mdac_typ.exe를 다운로드할 수도 있습니다.  
  
 자세한 내용을 보려면 [MSDN](http://go.microsoft.com/fwlink/p/?linkid=198016) 웹 사이트에서 "MDAC 2.8 SP1 재배포"를 검색하세요. Visual Studio 설치 프로젝트를 사용하여 응용 프로그램을 배포하는 경우 [배포 및 종속성](http://msdn.microsoft.com/en-us/49e9b84d-bd6a-4388-b9ac-46ea79cf0733)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 파일 재배포](../ide/redistributing-visual-cpp-files.md)