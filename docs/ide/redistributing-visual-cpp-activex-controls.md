---
title: "Visual c + + ActiveX 컨트롤 재배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [C++], redistributing
- controls [C++], distributing
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c520d365a259c36baab8edeb9049aab9ac89925a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-visual-c-activex-controls"></a>Visual C++ ActiveX 컨트롤 재배포
Visual c + + 6.0 제공 ActiveX 컨트롤 다음 다시 배포 하는 응용 프로그램에서 사용할 수 있습니다. 이러한 컨트롤은 더 이상 Visual c + +에 포함 됩니다. Visual c + + 6.0에 대 한 사용권 계약에 따라 Visual c + +에서 개발 된 응용 프로그램으로 이러한 컨트롤을 재배포할 수 있습니다.  
  
> [!NOTE]
>  Visual c + + 6.0은 더 이상 Microsoft에서 지원 됩니다.  
  
 재배포 가능한 Visual c + + 6.0 ActiveX 컨트롤 목록은 Visual c + + 6.0 제품 CD의 디스크 1에서 Common\Redist\Redist.txt를 참조 하세요.  
  
 응용 프로그램을 배포 하는 경우 설치 하 고 (Regsvr32.exe를 사용 하 여) ActiveX 컨트롤에 대 한.ocx 등록 해야 합니다. 또한 대상 컴퓨터 (별표 등록 해야 하는 파일을 나타냄) 다음과 같은 시스템 파일의 현재 버전에 설치 되었는지 확인 해야 합니다.  
  
-   asycfilt.dll  
  
-   Comcat.dll *  
  
-   Oleaut32.dll *  
  
-   Olepro32.dll *  
  
-   stdole2.tlb  
  
 이러한 Dll을 대상 시스템에서 사용할 수 없는 경우 해당 운영 체제를 업데이트 하기 위한 미리 지정된 된 메커니즘을 사용 하 여 업데이트 해야 합니다. Windows 운영 체제에 대 한 최신 서비스 팩을 다운로드할 수 [http://windowsupdate.microsoft.com](http://windowsupdate.microsoft.com)합니다.  
  
 응용 프로그램 데이터베이스에 연결 하는 ActiveX 컨트롤 중 하나를 사용 하는 Microsoft 데이터 액세스 구성 요소 (MDAC) 대상 시스템에 설치 되어 있어야 합니다. 자세한 내용은 참조 [데이터베이스 지원 파일 재배포](../ide/redistributing-database-support-files.md)합니다.  
  
 데이터베이스에 연결 하는 ActiveX 컨트롤을 사용할 경우 대상 컴퓨터에 데이터 원본 이름을 복제 해야 하는 또한 합니다. 이렇게 하려면 프로그래밍 방식으로 함수를 사용한와 같은 `ConfigDSN`합니다.  
  
 추가 종속성이 있는 일부 재배포 가능한 ActiveX 컨트롤입니다. 각.ocx 파일 Os\System 폴더에는 Visual c + + 6.0 제품 CD에는.dep 파일 도입니다. 재배포 하려는 각.ocx 파일에 대 한 해당.dep 파일에 하나 이상의 사용 하 여 항목을 찾습니다. 파일이 나열 되어 대상 컴퓨터에 파일이 있는지 확인 해야 합니다. .Ocx 파일을 직접 지 원하는 모든 Dll을 등록 해야 합니다. (성공 하려면 Regsvr32.exe, 대상 컴퓨터 먼저 있어야 모든 컨트롤에서 정적으로 로드 한 Dll입니다.) 또한 종속 항목으로 나열 된 DLL은 Visual c + + 6.0 cd Os\System 폴더에.dep 파일이, 사용 하 여 항목에 대 한 해당.dep 파일을 조사 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 파일 재배포](../ide/redistributing-visual-cpp-files.md)